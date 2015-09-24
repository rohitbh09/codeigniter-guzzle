Guzzle~6.0  installation in Codeigniter 2.2
============================================


## Installing Guzzle

The recommended way to install Guzzle is Guzzle installation Document


Or Please follow the following steps to install

Install Guzzle is git

```bash
# Install guzzle files in application/libraries folder

git clone git@github.com:guzzle/guzzle.git

```
Now vendor and guzzel.php files successfully install libraries


Please use following code to access guzzle 

```bash
  #guzzle library add to use guzzle
  $this->load->library('guzzle');

  # guzzel client define
  $client     = new GuzzleHttp\Client();
  
  #This url define speific Target for guzzel
  $url        = 'http://www.google.com';

  #Guzzel
  try {
    # Guzzel post request example with form parameter
    $response = $client->request( 'POST', 
                                   $url, 
                                  [ 'form_params' 
                                        => [ 'processId' => '2' ] 
                                  ]
                                );
    #guzzel repose for future use
    echo $response->getStatusCode(); // 200
    echo $response->getReasonPhrase(); // OK
    echo $response->getProtocolVersion(); // 1.1
    echo $response->getBody();
  } catch (GuzzleHttp\Exception\BadResponseException $e) {
    #guzzel repose for future use
    $response = $e->getResponse();
    $responseBodyAsString = $response->getBody()->getContents();
    print_r($responseBodyAsString);
  }


```