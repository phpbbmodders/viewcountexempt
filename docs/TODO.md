# TODO

## Waiting on phpBB

- File the tracker ticket for [`core.viewtopic_modify_view_counter_update`](events/viewtopic_modify_view_counter_update.txt) and open the phpBB core pull request.
- Once a phpBB release includes the event, raise the minimum phpBB version in `composer.json` and `ext.php` to that release.

## Build the extension

- Listener on `core.viewtopic_modify_view_counter_update` that sets `update_view_counters` to false when any of the rules below apply.
- `u_viewcountexempt` user permission ("Views do not count"), no one has it by default.
- ACP settings (both off by default, so nothing changes until an admin turns them on):
  - Topic authors don't add views to their own topics (`topic_data['topic_poster']`).
  - Administrators don't add views.
- Decide whether exempt views should still add to inline attachment download counts (the event allows counting one but not the other).
- Migration for the permission and config values, ACP module and language strings.
- Unit tests for the listener and a runtime check on a seed-forum test board.
- Add an `extra.version-check` block once the extension has a phpBB.com listing.
