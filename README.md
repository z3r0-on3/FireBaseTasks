# FireBaseTasks
A small app using firebase database to put\remove tasks from task list.


The firebase database rules are:
-[
{
  "rules": {
    "users": {
      "$uid": {
        ".read": "auth != null && auth.uid == $uid",
        ".write": "auth != null && auth.uid == $uid",
        "items": {
          "$item_id": {
            "title": {
              ".validate": "newData.isString() && newData.val().length > 2"
            }
          }
        }
      }
    }
  }
}
]-

