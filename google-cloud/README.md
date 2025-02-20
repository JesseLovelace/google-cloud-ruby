# google-cloud

The [google-cloud](https://github.com/googleapis/google-cloud-ruby/tree/master/google-cloud)
gem is a convenience package that lazily loads the vast majority of the
[google-cloud-*](https://github.com/googleapis/google-cloud-ruby) gems.
Because there are now so many google-cloud-* gems, instead of using this gem in
your production application, we encourage you to directly require only the
individual google-cloud-* gems that you need.

- [google-cloud API documentation](https://googleapis.dev/ruby/google-cloud/latest)
- [google-cloud on RubyGems](https://rubygems.org/gems/google-cloud)

## List of dependencies

This gem depends on and lazily loads the following google-cloud-* gems:

- [google-cloud-asset](https://github.com/googleapis/google-cloud-ruby/google-cloud-asset
- [google-cloud-bigquery](https://github.com/googleapis/google-cloud-ruby/google-cloud-bigquery
- [google-cloud-bigquery-data_transfer](https://github.com/googleapis/google-cloud-ruby/google-cloud-bigquery-data_transfer
- [google-cloud-bigtable](https://github.com/googleapis/google-cloud-ruby/google-cloud-bigtable
- [google-cloud-container](https://github.com/googleapis/google-cloud-ruby/google-cloud-container
- [google-cloud-dataproc](https://github.com/googleapis/google-cloud-ruby/google-cloud-dataproc
- [google-cloud-datastore](https://github.com/googleapis/google-cloud-ruby/google-cloud-datastore
- [google-cloud-dialogflow](https://github.com/googleapis/google-cloud-ruby/google-cloud-dialogflow
- [google-cloud-dlp](https://github.com/googleapis/google-cloud-ruby/google-cloud-dlp
- [google-cloud-dns](https://github.com/googleapis/google-cloud-ruby/google-cloud-dns
- [google-cloud-error_reporting](https://github.com/googleapis/google-cloud-ruby/google-cloud-error_reporting
- [google-cloud-firestore](https://github.com/googleapis/google-cloud-ruby/google-cloud-firestore
- [google-cloud-kms](https://github.com/googleapis/google-cloud-ruby/google-cloud-kms
- [google-cloud-language](https://github.com/googleapis/google-cloud-ruby/google-cloud-language
- [google-cloud-logging](https://github.com/googleapis/google-cloud-ruby/google-cloud-logging
- [google-cloud-monitoring](https://github.com/googleapis/google-cloud-ruby/google-cloud-monitoring
- [google-cloud-os_login](https://github.com/googleapis/google-cloud-ruby/google-cloud-os_login
- [google-cloud-pubsub](https://github.com/googleapis/google-cloud-ruby/google-cloud-pubsub
- [google-cloud-redis](https://github.com/googleapis/google-cloud-ruby/google-cloud-redis
- [google-cloud-resource_manager](https://github.com/googleapis/google-cloud-ruby/google-cloud-resource_manager
- [google-cloud-scheduler](https://github.com/googleapis/google-cloud-ruby/google-cloud-scheduler
- [google-cloud-spanner](https://github.com/googleapis/google-cloud-ruby/google-cloud-spanner
- [google-cloud-speech](https://github.com/googleapis/google-cloud-ruby/google-cloud-speech
- [google-cloud-storage](https://github.com/googleapis/google-cloud-ruby/google-cloud-storage
- [google-cloud-tasks](https://github.com/googleapis/google-cloud-ruby/google-cloud-tasks
- [google-cloud-text_to_speech](https://github.com/googleapis/google-cloud-ruby/google-cloud-text_to_speech
- [google-cloud-trace](https://github.com/googleapis/google-cloud-ruby/google-cloud-trace
- [google-cloud-translate](https://github.com/googleapis/google-cloud-ruby/google-cloud-translate
- [google-cloud-video_intelligence](https://github.com/googleapis/google-cloud-ruby/google-cloud-video_intelligence
- [google-cloud-vision](https://github.com/googleapis/google-cloud-ruby/google-cloud-vision

## Quick Start

```sh
$ gem install google-cloud
```

## Authentication

Instructions and configuration options are covered in the [Authentication
Guide](https://googleapis.dev/ruby/google-cloud/latest/file.AUTHENTICATION.html).

## Example

As shown in the example below, the google-cloud gem lazily loads its
google-cloud-* dependencies only as needed.

```ruby
require "google-cloud"

gcloud = Google::Cloud.new

Google::Cloud::Bigquery #=> NameError: uninitialized constant Google::Cloud::Bigquery

bigquery = gcloud.bigquery

Google::Cloud::Bigquery #=> Google::Cloud::Bigquery
Google::Cloud::Logging #=> NameError: uninitialized constant Google::Cloud::Logging

dataset = bigquery.dataset "my-dataset"
table = dataset.table "my-table"
table.data.each do |row|
  puts row
end
```

## Supported Ruby Versions

This library is supported on Ruby 2.3+.

Google provides official support for Ruby versions that are actively supported
by Ruby Core—that is, Ruby versions that are either in normal maintenance or in
security maintenance, and not end of life. Currently, this means Ruby 2.3 and
later. Older versions of Ruby _may_ still work, but are unsupported and not
recommended. See https://www.ruby-lang.org/en/downloads/branches/ for details
about the Ruby support schedule.

## Versioning

This library follows [Semantic Versioning](http://semver.org/).

It is currently in major version zero (0.y.z), which means that anything may
change at any time and the public API should not be considered stable.

## Contributing

Contributions to this library are always welcome and highly encouraged.

See the [Contributing
Guide](https://googleapis.dev/ruby/google-cloud/latest/file.CONTRIBUTING.html)
for more information on how to get started.

Please note that this project is released with a Contributor Code of Conduct. By
participating in this project you agree to abide by its terms. See [Code of
Conduct](https://googleapis.dev/ruby/google-cloud/latest/file.CODE_OF_CONDUCT.html)
for more information.

## License

This library is licensed under Apache 2.0. Full license text is available in
[LICENSE](https://googleapis.dev/ruby/google-cloud/latest/file.LICENSE.html).

## Support

Please [report bugs at the project on
Github](https://github.com/googleapis/google-cloud-ruby/issues). Don't
hesitate to [ask
questions](http://stackoverflow.com/questions/tagged/google-cloud-platform+ruby)
about the client or APIs on [StackOverflow](http://stackoverflow.com).
