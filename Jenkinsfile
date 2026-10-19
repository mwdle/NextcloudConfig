@Library("JenkinsPipelines") _ // See https://github.com/mwdle/JenkinsPipelines

boolean disableIndexTriggers = env.BRANCH_NAME != 'main'

quadletPipeline(
    disableIndexTriggers: disableIndexTriggers,
    podmanSecretMappings: [
        [
            type: 'usernamePassword',
            credentialsId: 'Nextcloud',
            podmanSecretUsernameName: 'nextcloud_admin_username',
            podmanSecretPasswordName: 'nextcloud_admin_password'
        ],
        [
            type: 'usernamePassword',
            credentialsId: 'nextcloud-db',
            podmanSecretUsernameName: 'nextcloud_db_username',
            podmanSecretPasswordName: 'nextcloud_db_password'
        ],
        [
            type: 'usernamePassword',
            credentialsId: 'Email noreply',
            podmanSecretUsernameName: 'lab_smtp_username',
            podmanSecretPasswordName: 'lab_smtp_password'
        ],
        [
            type: 'string',
            credentialsId: 'nextcloud-mail-domain',
            podmanSecretStringName: 'nextcloud_mail_domain'
        ]
    ]
)
