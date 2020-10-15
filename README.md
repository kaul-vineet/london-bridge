## london-bridge

A simple app that streams Kafka messages down a web page.

#### Development Setup
```shell
npm install
```
Additionally these environment variables need to be defined:

- `KAFKA_URL`: A comma separated list of SSL URLs to the Kafka brokers making up the cluster.
- `KAFKA_CLIENT_CERT`: The required client certificate (in PEM format) to authenticate clients against the broker.
- `KAFKA_CLIENT_CERT_KEY`: The required client certificate key (in PEM format) to authenticate clients against the broker.
- `KAFKA_TOPIC`: The Kafka topic from which to consume

#### Development Running
```shell
npm start
```
Open http://localhost:3000 in a browser and watch tweets stream in...

#### Deploy
```shell
git clone git@github.com:crcastle/kafka-message-waterfall.git
cd kafka-message-waterfall
heroku create
git push heroku master
```
You can define the below environment variables manually, or you can run this command to define them from another app that already has a Kafka cluster attached: `heroku addons:attach my-originating-app::KAFKA` (where "my-originating-app" is the app to which the cluster is already attached)

Or manually:
```
heroku config:set KAFKA_URL=
heroku config:set KAFKA_CLIENT_CERT=
heroku config:set KAFKA_CLIENT_CERT_KEY=
heroku config:set KAFKA_TOPIC=
```
