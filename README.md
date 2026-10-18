# View Count Exempt

[![Tests](https://github.com/phpbbmodders/viewcountexempt/actions/workflows/tests.yml/badge.svg)](https://github.com/phpbbmodders/viewcountexempt/actions/workflows/tests.yml) [![Lint](https://github.com/phpbbmodders/viewcountexempt/actions/workflows/lint.yml/badge.svg)](https://github.com/phpbbmodders/viewcountexempt/actions/workflows/lint.yml)

Stops chosen users, admins and topic authors from adding to topic view counts.

## Status

**Not usable yet.** phpBB has no event at the point where `viewtopic.php` adds to a topic's view count, so an extension cannot change it without editing core files. This extension is waiting for that event to be added to phpBB. The request is in [`docs/events/viewtopic_modify_view_counter_update.txt`](docs/events/viewtopic_modify_view_counter_update.txt).

Requested on phpBB.com: [Prevent view count increasing](https://www.phpbb.com/community/viewtopic.php?p=16140973#p16140973).

## Planned features

- A **Views do not count** permission, so admins can pick any users or groups whose topic views are not counted.
- An ACP setting so topic authors don't add views to their own topics.
- An ACP setting so administrators don't add views.

## Requirements

- phpBB 3.3.19 or later (plus the phpBB release that adds the event above)
- PHP 7.4 or later

## TODO

Ideas not yet built, practical and speculative alike: [`docs/TODO.md`](docs/TODO.md).

## Contributing

Contributions are welcome!

- **Bug reports**: [Open an issue](https://github.com/phpbbmodders/viewcountexempt/issues).
- **Everything else** (questions, feature requests, ideas, general discussion): [Use Discussions](https://github.com/orgs/phpbbmodders/discussions), or the [community forum](https://www.phpbbmodders.com/community/).
- Pull requests are welcome for bug fixes or discussed features.

## Acknowledgments

- Code review, bug fixes, and documentation assisted by [Claude](https://www.anthropic.com/claude).

## License

This extension is licensed under the **GNU General Public License v2.0**.

See [license.txt](license.txt) for more information.
