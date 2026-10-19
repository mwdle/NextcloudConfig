@Library("JenkinsPipelines") _ // See https://github.com/mwdle/JenkinsPipelines

boolean disableIndexTriggers = env.BRANCH_NAME != 'main'

quadletPipeline(
    disableIndexTriggers: disableIndexTriggers,
    podmanSecretMappings: [
        [
            type: 'usernamePassword',
            credentialsId: 'Nextcloud',
            podmanSecretPasswordName: 'nextcloud_admin_password',
            podmanSecretUsernameName: 'nextcloud_admin_username'
        ],
        [
            type: 'usernamePassword',
            credentialsId: 'nextcloud-db',
            podmanSecretPasswordName: 'nextcloud_db_password',
            podmanSecretUsernameName: 'nextcloud_db_username'
        ],
        [
            type: 'usernamePassword',
            credentialsId: 'Email noreply',
            podmanSecretPasswordName: 'lab_smtp_password',
            podmanSecretUsernameName: 'lab_smtp_username'
        ],
        [
            type: 'string',
            credentialsId: 'nextcloud-mail-domain',
            podmanSecretStringName: 'nextcloud_mail_domain'
        ]
    ]
)
