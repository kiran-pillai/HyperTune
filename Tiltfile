docker_compose('docker-compose.yml')

dc_resource('postgres')
dc_resource(
    'hypertune-api',
    resource_deps=['postgres'],
    labels=['api'],
    links=[
        link('http://localhost:8000', 'hypertune-api'),
        link('postgres://postgres:postgres@localhost:5432/hypertune', 'postgres'),
    ],
)
dc_resource(
    'hypertune-ui',
    resource_deps=['hypertune-api'],
    labels=['ui'],
    links=[
        link('http://localhost:5173', 'hypertune-ui'),
    ],
)
