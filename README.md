Guzzel~6.0  installation in Codeigniter 2.2
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
  // guzzel library add to use guzzle
  $this->load->library('guzzel');

  // guzzel start
  $client     = new GuzzleHttp\Client();
  $url        = 'http://www.google.com';
  try {
    $response = $client->request('POST', $url, [ 'form_params' => [ 'processId' => '2' ] ]);
    echo $response->getStatusCode(); // 200
    echo $response->getReasonPhrase(); // OK
    echo $response->getProtocolVersion(); // 1.1
    echo $response->getBody();
  } catch (GuzzleHttp\Exception\BadResponseException $e) {
   $response = $e->getResponse();
    $responseBodyAsString = $response->getBody()->getContents();
    print_r($responseBodyAsString);
  }
```