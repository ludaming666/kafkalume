# KafkaLume Privacy Policy

Updated: October 31, 2026

Publisher: ludaming666 (GitHub: https://github.com/ludaming666)  
Project homepage: https://github.com/ludaming666/kafkalume  
Report an issue: https://github.com/ludaming666/kafkalume/issues  
Contact email: kafkalume@gmail.com

## Scope

This policy applies to the KafkaLume Windows desktop preview. KafkaLume is a local tool that connects directly to services specified by the user. It does not provide developer-operated accounts or cloud synchronization.

## Data processed locally

- Connection settings: connection names, Broker and Schema Registry addresses, authentication settings, and passwords and certificates supplied by the user.
- Usage records: alerts and recoveries, lag trends, operation audits, message replay and configuration history, related local backups, and interface settings.
- Kafka data: topics, consumer groups, schemas, and message contents viewed by the user are processed and displayed in the application. Content is written to a target service or local file only when the user initiates an operation such as sending, replaying, or exporting.

Newly saved passwords, certificates, and bot credentials are stored using local encryption provided by Windows. Other local records, automatic alert backups, and exported files are not guaranteed to be encrypted. Protect your Windows account and exported files, and do not publish backups or screenshots containing sensitive information.

## Data transmission

- The application communicates with Kafka Brokers configured by the user. Sending or replaying messages, creating or deleting topics, adjusting consumer offsets, and similar operations transmit data or commands to the selected cluster.
- When Schema Registry is configured, the application communicates with that address. Configured authentication credentials accompany requests to that service. Prefer HTTPS.
- Only when the user enables and configures bot notifications does the application send connection names, alert titles, descriptions, timestamps, and similar information to the selected Feishu, DingTalk, or WeCom bot. Alert text may include topic or consumer group names. Notifications do not include Kafka message bodies or connection passwords.
- This version is not designed to automatically upload usage statistics, crash reports, or Kafka data to a publisher-operated server. Windows notifications and the third-party services above may still process information under their own policies.

Kafka PLAINTEXT connections and HTTP Schema Registry connections may be unencrypted. Connection security depends on the user and target service settings. KafkaLume does not automatically convert them into secure connections.

## Storage, export, and deletion

Application data is stored by default in %APPDATA%\kafka-lens-desktop for the current Windows user. This directory is retained after the rename to preserve existing data. An explicit --user-data-dir option overrides the default. User exports are saved at the location the user selects. Some records are retained or overwritten according to feature-specific rules; alert records and backups may remain locally.

Deleting a connection in the application does not delete all related history or exported files. To remove local application data completely, first exit KafkaLume and back up anything you want to keep, then delete the application data directory above. Delete exported files separately. Connection settings, alerts, and other local records may not be recoverable after deletion.

## Contact and updates

Send questions using the GitHub Issues page above or email kafkalume@gmail.com. Do not include passwords, certificates, message bodies, or other sensitive information in feedback, especially in public issues. We will update this policy and its date when features or data flows change materially.
