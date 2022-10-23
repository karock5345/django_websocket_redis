Websocket simple testing project.
install Channels, redis
Windows do not support Redis directy. It can be install 3rd party software for Windows development test.
Download and install Memurai : memurai.com/get-memurai 
Channels v4.0.0 do not support this tutorial, should be force install v3.0.5
And for safety, install redis v3.4.1
Install Lib:
> .\env\scripts\activate
> python -m pip install -Iv channels==3.0.5
> python -m pip install -Iv channels-redis==3.4.1

Difference between user Redis / not
is settings.py ->

ASGI_APPLICATION = 'application_name.asgi.application'

CHANNEL_LAYERS = {
    'default':{
        'BACKEND':'channels.layers.InMemoryChannelLayer'
    }
}

////////////////////////////////////

ASGI_APPLICATION = 'application_name.asgi.application'

CHANNEL_LAYERS = {
    'default':{
        'BACKEND':'channels_redis.core.RedisChannelLayer',
        'CONFIG': {
            'hosts':[('127.0.0.1', '6379')],
        },
    }
}