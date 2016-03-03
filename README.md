# Poppy-Humamoid
Starting Porblems with Poppy Humanoid Robot

Hello everybody,
I just tried to make Poppy move, but i got following Problems:
Running this code :
"from poppy.creatures import PoppyHumanoid
poppy = PoppyHumanoid()"
it just says
"WindowsError                              Traceback (most recent call last)
<ipython-input-4-8559991d5db6> in <module>()
      1 from poppy.creatures import PoppyHumanoid
----> 2 poppy = PoppyHumanoid()

C:\Users\Kevin\Anaconda2\lib\site-packages\poppy\creatures\abstractcreature.pyc in __new__(cls, base_path, config, simulator, scene, host, port, id, use_snap, snap_host, snap_port, snap_quiet, use_http, http_host, http_port, http_quiet, use_remote, remote_host, remote_port, sync)
     98         else:
     99             try:
--> 100                 poppy_creature = from_json(config, sync)
    101             except IndexError as e:
    102                 raise IOError('Connection to the robot failed! {}'.format(e.message))

C:\Users\Kevin\Anaconda2\lib\site-packages\pypot\robot\config.pyc in from_json(json_file, sync, strict, use_dummy_io)
    242         config = json.load(f)
    243 
--> 244     return from_config(config, sync=sync, strict=strict, use_dummy_io=use_dummy_io)
    245 
    246 

C:\Users\Kevin\Anaconda2\lib\site-packages\pypot\robot\config.pyc in from_config(config, strict, sync, use_dummy_io)
     58         attached_ids = [m.id for m in attached_motors]
     59         if not use_dummy_io:
---> 60             dxl_io = dxl_io_from_confignode(config, c_params, attached_ids, strict)
     61 
     62             check_motor_limits(config, dxl_io, motor_names)

C:\Users\Kevin\Anaconda2\lib\site-packages\pypot\robot\config.pyc in dxl_io_from_confignode(config, c_params, ids, strict)
    137 
    138     if port == 'auto':
--> 139         port = pypot.dynamixel.find_port(ids, strict)
    140         logger.info('Found port {} for ids {}'.format(port, ids))
    141 

C:\Users\Kevin\Anaconda2\lib\site-packages\pypot\dynamixel\__init__.pyc in find_port(ids, strict)
     81     """
     82     ids_founds = []
---> 83     for port in get_available_ports():
     84         for DxlIOCls in (DxlIO, Dxl320IO):
     85             try:

C:\Users\Kevin\Anaconda2\lib\site-packages\pypot\dynamixel\__init__.pyc in get_available_ports(only_free)
     47 
     48 def get_available_ports(only_free=False):
---> 49     ports = _get_available_ports()
     50 
     51     if only_free:

C:\Users\Kevin\Anaconda2\lib\site-packages\pypot\dynamixel\__init__.pyc in _get_available_ports()
     34         ports = []
     35         path = 'HARDWARE\\DEVICEMAP\\SERIALCOMM'
---> 36         key = _winreg.OpenKey(_winreg.HKEY_LOCAL_MACHINE, path)
     37 
     38         for i in itertools.count():

WindowsError: [Error 2] Das System kann die angegebene Datei nicht finden
"

I tried nearly everthing an i don´t know what to to.
Thank you for your help 
