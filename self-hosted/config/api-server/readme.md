| api-server\appsettings.production.json                                                                             | Description                                                                                                     |
|--------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------|
| {                                                                                                                  |                                                                                                                 |
|   "ConnectionStrings": {                                                                                           |                                                                                                                 |
|     "TwApiDatabase": "Server=?????;Database=?????;User Id=?????;Password=?????;MultipleActiveResultSets=True;",    | Login server database SQL connection string.                                                                    |
|     "HangfireDatabase": "Server=?????;Database=?????;User Id=?????;Password=?????;MultipleActiveResultSets=True;", | Hangfire database SQL connection string.                                                                        |
|     "RebusDatabase": "Server=?????;Database=?????;User Id=?????;Password=?????;MultipleActiveResultSets=True;",    | Rebus database SQL connection string.                                                                           |
|     "Redis": "redis",                                                                                              | Redis connection string - usually just the service name (ex: "redis") in a single-host system.                  |
|     "SovrenSrpsUrl": "http://srps",                                                                                | Base URL of the the Sovren resume parser service.  This may be a service name in a single-host system.          |
|     "ConvertServiceUrl": "http://convert",                                                                         | Base URL of the the convert (document conversion) service.  This may be a service name in a single-host system. |
|     "AuthorityUrl": "http://login",                                                                                | Externally-accessible base URL of the login server.                                                             |
|     "EmailServiceUrl": "http://api-email-server"                                                                   | Base URL of the the email service.  This may be a service name in a single-host system.                         |
|   },                                                                                                               |                                                                                                                 |
|   "AppSettings": {                                                                                                 |                                                                                                                 |
|     "OrganizationName": "??????-Supplied-by-TempworksSoftware",                                                    |                                                                                                                 |
|     "AuthorityRequireHttpsMetadata": "false",                                                                      | Enforce that a HTTPS authority service URL is used.                                                             |
|     "MaximumFileUploadSizeBytes": "26214400",                                                                      | File uploads exceeding this size (in bytes) are rejected (26214400 bytes equals 25 megabytes).                  |
|     "RunHangfireServer": "False",                                                                                  | Start a Hangfire background worker process with for this service.                                               |
|     "SharedTempDirectory": "C:\\app\\shared-temp"                                                                  |                                                                                                                 |
|   },                                                                                                               |                                                                                                                 |
|   "Serilog": {                                                                                                     | Logging settings for Serilog logging framework (see: <https://serilog.net>).                                    |
|     "MinimumLevel": {                                                                                              |                                                                                                                 |
|       "Default": "Information"                                                                                     |                                                                                                                 |
|     },                                                                                                             |                                                                                                                 |
|     "Enrich": [ "FromLogContext", "WithMachineName", "WithThreadId" ],                                             |                                                                                                                 |
|     "WriteTo": [                                                                                                   |                                                                                                                 |
|       {                                                                                                            |                                                                                                                 |
|         "Name": "LiterateConsole",                                                                                 |                                                                                                                 |
|         "Args": { "outputTemplate": "[{Timestamp:HH:mm:ss} [{Level}] ({ThreadId}) {Message}{NewLine}{Exception}" } |                                                                                                                 |
|       },                                                                                                           |                                                                                                                 |
|       {                                                                                                            |                                                                                                                 |
|         "Name": "RollingFile",                                                                                     |                                                                                                                 |
|         "Args": {                                                                                                  |                                                                                                                 |
|           "pathFormat": "logs\\api-server-{Date}.txt",                                                             |                                                                                                                 |
|           "shared": true,                                                                                          |                                                                                                                 |
|           "retainedFileCountLimit": 3,                                                                             |                                                                                                                 |
|           "outputTemplate": "{Timestamp:o} [{Level:u3}] ({MachineName}/{ThreadId}) {Message}{NewLine}{Exception}"  |                                                                                                                 |
|         }                                                                                                          |                                                                                                                 |
|       }                                                                                                            |                                                                                                                 |
|     ]                                                                                                              |                                                                                                                 |
|   }                                                                                                                |                                                                                                                 |
| }                                                                                                                  |                                                                                                                 |