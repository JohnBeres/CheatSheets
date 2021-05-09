# Basic Queries
| KQL | Notes |
| :---: | :---: |
| event_id:1 | Process Create events |
| event_id:3 | Network Connect events |
| Image:\*chrome.exe | All events that Google Chrome generated |
| ParentImage:\*cmd.exe AND event_id:1 | All programs launched from a command shell |
| Image:\*cmd.exe AND ParentImage:\*chrome.exe | Chrome launched a command shell |

# Advanced Queries
| KQL | Notes |
| :---: | :---: |
