Guzzle~6.0  installation in Codeigniter 2.2
============================================


## Installing Guzzle

The recommended way to install Guzzle is Guzzle installation Document


Or Please follow the following steps to install

Install Guzzle is git

```bash
# Install guzzle files in application/libraries folder

git clone https://github.com/rohitbh09/codeigniter-guzzle.git

```
Now vendor and guzzle.php files successfully install libraries


Please use following code to access guzzle 

```bash
  #guzzle library add to use guzzle
  $this->load->library('guzzle');

  # guzzle client define
  $client     = new GuzzleHttp\Client();
  
  #This url define speific Target for guzzle
  $url        = 'http://www.google.com';

  #guzzle
  try {
    # guzzle post request example with form parameter
    $response = $client->request( 'POST', 
                                   $url, 
                                  [ 'form_params' 
                                        => [ 'processId' => '2' ] 
                                  ]
                                );
    #guzzle repose for future use
    echo $response->getStatusCode(); // 200
    echo $response->getReasonPhrase(); // OK
    echo $response->getProtocolVersion(); // 1.1
    echo $response->getBody();
  } catch (GuzzleHttp\Exception\BadResponseException $e) {
    #guzzle repose for future use
    $response = $e->getResponse();
    $responseBodyAsString = $response->getBody()->getContents();
    print_r($responseBodyAsString);
  }


```