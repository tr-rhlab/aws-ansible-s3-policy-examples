# Changelog

All notable changes to this project are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [1.0.0] - 2026-10-12

### Added

- `retrieve_s3_bucket_policy.yml` reads one bucket policy with `amazon.aws.s3_bucket_info` and prints the document and the public-access flag.
- `create_s3_bucket_policy.yml` creates the bucket when it is missing and sets a policy written in the playbook. It requires a non-empty `policy` extra var before the write. Account, role, and bucket name are variables.
- `create_s3_bucket_policy_from_file.yml` creates the bucket when it is missing and sets a policy loaded from a JSON file. `lookup('ansible.builtin.template')` renders the file first, so it can include Jinja2, and `from_json` parses the result. The playbook fails before the write when a `Resource` omits the bucket name.
- `policies/allow-list-and-read.json`, a sample policy that lets `AppReader` list and read objects and denies requests that are not HTTPS.
- `collections/requirements.yml`, which installs `amazon.aws` 9.0.0 or newer.
- A README with requirements, a customer demo, and a fakecloud rehearsal.

[Unreleased]: https://github.com/tr-rhlab/aws-ansible-examples/compare/v1.0.0...HEAD
[1.0.0]: https://github.com/tr-rhlab/aws-ansible-examples/releases/tag/v1.0.0
