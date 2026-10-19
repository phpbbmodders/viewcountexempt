# TODO

## Waiting on phpBB

- Wait for [`core.viewtopic_modify_view_counter_update`](events/viewtopic_modify_view_counter_update.txt) to be merged: tracker ticket [PHPBB-17745](https://tracker.phpbb.com/browse/PHPBB-17745), pull request [phpbb/phpbb#7092](https://github.com/phpbb/phpbb/pull/7092).
- Once a phpBB release includes the event, raise the minimum phpBB version in `composer.json` and `ext.php` to that release.

## Build the extension

- Listener on `core.viewtopic_modify_view_counter_update` that sets `update_view_counters` to false when any of the rules below apply.
- `u_viewcountexempt` user permission ("Views do not count"), no one has it by default.
- ACP settings (all off by default, so nothing changes until an admin turns them on):
  - Topic authors don't add views to their own topics (`topic_data['topic_poster']`).
  - Administrators don't add views.
  - Optional: count only the first view of a topic in a session. phpBB's own repeat-view check looks for `'&t=' . $topic_id` in `session_page`, so reloads of `viewtopic.php?t=N` and `viewtopic.php?p=N` (the links phpBB itself makes) count every time, and a view of topic 1 right after topic 12 is skipped. A maintainer said in [PHPBB-16989](https://tracker.phpbb.com/browse/PHPBB-16989) that counting every view is intended, so this would be opt-in. Matching `t=` as a whole value and mapping `p=` to its topic would fix both cases.
- Decide whether exempt views should still add to inline attachment download counts (the event allows counting one but not the other).
- Migration for the permission and config values, ACP module and language strings.
- Unit tests for the listener and a runtime check on a seed-forum test board.
- Add an `extra.version-check` block once the extension has a phpBB.com listing.
