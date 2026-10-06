* `Free Text Search` - Searches for matching words across all fields without specifying a field name.
  Command:
  index=windowslogs alice


* `fields` - Selects only specific fields to improve query performance and keep results clean.
  Command:
  index=windowslogs | fields host User SourceIp


* `dedup` - Removes duplicate events based on specified fields to show only unique entries.
  Command:
  index=windowslogs | fields EventID User Image Hostname SourceIp | dedup SourceIp


* `rename` - Renames a field in the search results for better display readability.
  Command:
  index=windowslogs | fields EventID User Image Hostname SourceIp | rename User as Employee


* `table` - Formats the selected fields into a clean column table view.
  Command:
  index=windowslogs | table _time EventID Hostname SourceName


* `Structuring Commands` - Restricts or reorders query output (`head` shows first N results, `tail` shows last N, `sort` orders results, `reverse` flips the result list).
  Command:
  index=windowslogs | head 10


* `Timelining With Table` - Displays timeline events in chronological order using `reverse`.
  Command:
  index=windowslogs Hostname=Salena.Adam | table _time Hostname EventID Category | reverse
