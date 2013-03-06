配置选项列表
============

可以在 php.ini 中使用下列配置选项对 PHP 进行配置。

“可修改范围”列决定了该配置选项在什么情况下可以被设置。 查看 可变配置选项 列表查看具体定义。


配置选项

===================================== =============================================== ============== ================================================================
名字                                   默认                                            可修改范围     更新日志
===================================== =============================================== ============== ================================================================
allow_call_time_pass_reference        "1"                                             PHP_INI_PERDIR 在 PHP 4.0.0 时是 PHP_INI_ALL    。 在 PHP 5.4.0 中移除该选项。
allow_url_fopen                       "1"                                             PHP_INI_SYSTEM 在 PHP <= 4.3.4 时是 PHP_INI_ALL    。
allow_url_include                     "0"                                             PHP_INI_ALL    在 PHP 5 时是 PHP_INI_SYSTEM。 从 PHP 5.2.0 起可用。
always_populate_raw_post_data         "0"                                             PHP_INI_PERDIR 在 PHP <= 4.2.3 时是 PHP_INI_ALL    。 从 PHP 4.1.0 起可用。
apc.cache_by_default                  "1"                                             PHP_INI_ALL    在 APC <= 3.0.12 时是 PHP_INI_SYSTEM。 从 APC 3.0.0 起可用。
apc.enabled                           "1"                                             PHP_INI_SYSTEM 在 APC 2 时是 PHP_INI_SYSTEM。 在 APC <= 3.0.12 时是 PHP_INI_ALL    。
apc.enable_cli                        "0"                                             PHP_INI_SYSTEM 从 APC 3.0.7 起可用。
apc.file_update_protection            "2"                                             PHP_INI_SYSTEM 从 APC 3.0.6 起可用。
apc.filters                           NULL                                            PHP_INI_SYSTEM
apc.gc_ttl                            "3600"                                          PHP_INI_SYSTEM
apc.include_once_override             "0"                                             PHP_INI_SYSTEM 从 APC 3.0.12 起可用。
apc.localcache                        "0"                                             PHP_INI_SYSTEM 从 APC 3.0.14 起可用。
apc.localcache.size                   "512"                                           PHP_INI_SYSTEM 从 APC 3.0.14 起可用。
apc.max_file_size                     "1M"                                            PHP_INI_SYSTEM 从 APC 3.0.7 起可用。
apc.mmap_file_mask                    NULL                                            PHP_INI_SYSTEM
apc.num_files_hint                    "1000"                                          PHP_INI_SYSTEM
apc.optimization                      "0"                                             PHP_INI_ALL    在 APC 2 时是 PHP_INI_SYSTEM。 在 APC 3.0.13 中移除该选项。
apc.report_autofilter                 "0"                                             PHP_INI_SYSTEM 从 APC 3.0.11 起可用。
apc.rfc1867                           "0"                                             PHP_INI_SYSTEM 从 APC 3.0.13 起可用。
apc.rfc1867_freq                      "0"                                             PHP_INI_SYSTEM
apc.rfc1867_name                      "APC_UPLOAD_PROGRESS"                           PHP_INI_SYSTEM
apc.rfc1867_prefix                    "upload_"                                       PHP_INI_SYSTEM
apc.shm_segments                      "1"                                             PHP_INI_SYSTEM
apc.shm_size                          "30"                                            PHP_INI_SYSTEM
apc.slam_defense                      "0"                                             PHP_INI_SYSTEM 从 APC 3.0.0 起可用。
apc.stat                              "1"                                             PHP_INI_SYSTEM 从 APC 3.0.10 起可用。
apc.stat_ctime                        "0"                                             PHP_INI_SYSTEM 从 APC 3.0.13 起可用。
apc.ttl                               "0"                                             PHP_INI_SYSTEM 从 APC 3.0.0 起可用。
apc.user_entries_hint                 "4096"                                          PHP_INI_SYSTEM 从 APC 3.0.0 起可用。
apc.user_ttl                          "0"                                             PHP_INI_SYSTEM 从 APC 3.0.0 起可用。
apc.write_lock                        "1"                                             PHP_INI_SYSTEM 从 APC 3.0.11 起可用。
apd.bitmask                           "0"                                             PHP_INI_ALL    在 apd 0.9 中移除该选项。
apd.dumpdir                           NULL                                            PHP_INI_ALL    
apd.statement_tracing                 "0"                                             PHP_INI_ALL    从 apd 0.9 起可用。
arg_separator                         "&"                                             PHP_INI_ALL    在 PHP 4.0.6 中移除该选项。
arg_separator.input                   "&"                                             PHP_INI_PERDIR 从 PHP 4.0.5 起可用。
arg_separator.output                  "&"                                             PHP_INI_ALL    从 PHP 4.0.5 起可用。
asp_tags                              "0"                                             PHP_INI_PERDIR 在 PHP 4.0.0 时是 PHP_INI_ALL    。
assert.active                         "1"                                             PHP_INI_ALL    
assert.bail                           "0"                                             PHP_INI_ALL    
assert.callback                       NULL                                            PHP_INI_ALL    
assert.quiet_eval                     "0"                                             PHP_INI_ALL    
assert.warning                        "1"                                             PHP_INI_ALL    
async_send                            "0"                                             PHP_INI_ALL    从 PHP 4.2.0 起可用。 在 PHP 4.3.0 中移除该选项。
auto_append_file                      NULL                                            PHP_INI_PERDIR 在 PHP <= 4.2.3 时是 PHP_INI_ALL    。
auto_detect_line_endings              "0"                                             PHP_INI_ALL    从 PHP 4.3.0 起可用。
auto_globals_jit                      "1"                                             PHP_INI_PERDIR 从 PHP 5.0.0 起可用。
auto_prepend_file                     NULL                                            PHP_INI_PERDIR 在 PHP <= 4.2.3 时是 PHP_INI_ALL    。
axis2.client_home                     "~/work/axisc/c/deply"                          PHP_INI_ALL    
axis2.enable_exception                "1"                                             PHP_INI_ALL    
axis2.enable_trace                    "1"                                             PHP_INI_ALL    
axis2.log_path                        "/tmp"                                          PHP_INI_ALL    
bcmath.scale                          "0"                                             PHP_INI_ALL    
bcompiler.enabled                     "1"                                             PHP_INI_ALL    从 bcompiler 0.8 起可用。
birdstep.max_links                    "-1"                                            PHP_INI_ALL    从 PHP 4.2.0 起可用。
blenc.key_file                        "/usr/local/etc/blenckeys"                      PHP_INI_ALL    
browscap                              NULL                                            PHP_INI_SYSTEM
cgi.check_shebang_line                "1"                                             PHP_INI_SYSTEM 从 PHP 5.2.1 起可用。
cgi.discard_path                      "0"                                             PHP_INI_SYSTEM 从 PHP 5.3.0 起可用。
cgi.fix_pathinfo                      "1"                                             PHP_INI_SYSTEM 在 PHP <= 5.2.0 时是 PHP_INI_ALL    。 从 PHP 4.3.0 起可用。
cgi.force_redirect                    "1"                                             PHP_INI_SYSTEM 在 PHP <= 5.2.0 时是 PHP_INI_ALL    。 从 PHP 4.2.0 起可用。
cgi.nph                               "0"                                             PHP_INI_ALL    从 PHP 4.3.5 起可用。
cgi.redirect_status_env               NULL                                            PHP_INI_SYSTEM 在 PHP <= 5.2.0 时是 PHP_INI_ALL    。 从 PHP 4.2.0 起可用。
cgi.rfc2616_headers                   "0"                                             PHP_INI_ALL    从 PHP 4.3.0 起可用。
child_terminate                       "0"                                             PHP_INI_ALL    从 PHP 4.0.5 起可用。
cli.pager                             ""                                              PHP_INI_ALL    从 PHP 5.4.0 起可用。
cli.prompt                            "\\b \\> "                                      PHP_INI_ALL    从 PHP 5.4.0 起可用。
cli_server.color                      "0"                                             PHP_INI_ALL    从 PHP 5.4.0 起可用。
coin_acceptor.autoreset               "On"                                            PHP_INI_ALL    在 coin_acceptor 0.2 中移除该选项。
coin_acceptor.auto_initialize         "Off"                                           PHP_INI_ALL    从 coin_acceptor 0.2 起可用。
coin_acceptor.auto_reset              "On"                                            PHP_INI_ALL    从 coin_acceptor 0.2 起可用。
coin_acceptor.command_function        "Off"                                           PHP_INI_ALL    从 coin_acceptor 0.3 起可用。
coin_acceptor.delay                   "53132"                                         PHP_INI_ALL    在 coin_acceptor 0.2 中移除该选项。
coin_acceptor.delay_coins             "53132"                                         PHP_INI_ALL    从 coin_acceptor 0.2 起可用。
coin_acceptor.delay_prom              "55748"                                         PHP_INI_ALL    从 coin_acceptor 0.2 起可用。
coin_acceptor.device                  "/dev/ttyS1"                                    PHP_INI_ALL    在 coin_acceptor 0.2 中移除该选项。
coin_acceptor.lock_on_close           "Off"                                           PHP_INI_ALL    从 coin_acceptor 0.2 起可用。
coin_acceptor.start_unlocked          "On"                                            PHP_INI_ALL    从 coin_acceptor 0.2 起可用。
com.allow_dcom                        "0"                                             PHP_INI_SYSTEM 从 PHP 4.0.5 起可用。
com.autoregister_casesensitive        "1"                                             PHP_INI_ALL    在 PHP 4 时是 PHP_INI_SYSTEM。从 PHP 4.1.0 起可用。
com.autoregister_typelib              "0"                                             PHP_INI_ALL    在 PHP 4 时是 PHP_INI_SYSTEM。 从 PHP 4.1.0 起可用。
com.autoregister_verbose              "0"                                             PHP_INI_ALL    在 PHP 4 时是 PHP_INI_SYSTEM。 从 PHP 4.1.0 起可用。
com.code_page                         ""                                              PHP_INI_ALL    从 PHP 5.0.0 起可用。
com.typelib_file                      ""                                              PHP_INI_SYSTEM 从 PHP 4.0.5 起可用。
crack.default_dictionary              NULL                                            PHP_INI_PERDIR 在 crack <= 0.2 时是 PHP_INI_SYSTEM。 从 PHP 4.0.5 起可用。 在 PHP 5.0.0 中移除该选项。
daffodildb.default_host               "localhost"                                     PHP_INI_ALL    
daffodildb.default_password           "daffodil"                                      PHP_INI_ALL    
daffodildb.default_socket             NULL                                            PHP_INI_ALL    
daffodildb.default_user               "DAFFODIL"                                      PHP_INI_ALL    
daffodildb.port                       "3456"                                          PHP_INI_ALL    
date.default_latitude                 "31.7667"                                       PHP_INI_ALL    从 PHP 5.0.0 起可用。
date.default_longitude                "35.2333"                                       PHP_INI_ALL    从 PHP 5.0.0 起可用。
date.sunrise_zenith                   "90.583333"                                     PHP_INI_ALL    从 PHP 5.0.0 起可用。
date.sunset_zenith                    "90.583333"                                     PHP_INI_ALL    从 PHP 5.0.0 起可用。
date.timezone                         ""                                              PHP_INI_ALL    从 PHP 5.1.0 起可用。
dba.default_handler                   ""                                              PHP_INI_ALL    从 PHP 4.3.3 起可用。
dbx.colnames_case                     "unchanged"                                     PHP_INI_SYSTEM 从 PHP 4.3.0 起可用。 在 PHP 5.1.0 中移除该选项。
default_charset                       ""                                              PHP_INI_ALL    
default_mimetype                      "text/html"                                     PHP_INI_ALL    
default_socket_timeout                "60"                                            PHP_INI_ALL    从 PHP 4.3.0 起可用。
define_syslog_variables               "0"                                             PHP_INI_ALL    在 PHP 5.4.0 中移除该选项。
detect_unicode                        "1"                                             PHP_INI_ALL    从 PHP 5.1.0 起可用。 此已废弃的 特性即将 被移除。
disable_classes                       ""                                              php.ini only   从 PHP 4.3.2 起可用。
disable_functions                     ""                                              php.ini only   从 PHP 4.0.1 起可用。
display_errors                        "1"                                             PHP_INI_ALL    
display_startup_errors                "0"                                             PHP_INI_ALL    从 PHP 4.0.3 起可用。
docref_ext                            ""                                              PHP_INI_ALL    从 PHP 4.3.2 起可用。
docref_root                           ""                                              PHP_INI_ALL    从 PHP 4.3.0 起可用。
doc_root                              NULL                                            PHP_INI_SYSTEM
enable_dl                             "1"                                             PHP_INI_SYSTEM 此已废弃的 特性即将 被移除。
engine                                "1"                                             PHP_INI_ALL    从 PHP 4.0.5 起可用。
error_append_string                   NULL                                            PHP_INI_ALL    
error_log                             NULL                                            PHP_INI_ALL    
error_prepend_string                  NULL                                            PHP_INI_ALL    
error_reporting                       NULL                                            PHP_INI_ALL    
etpan.default.charset                 "utf-8"                                         PHP_INI_ALL    
etpan.default.protocol                "imap"                                          PHP_INI_ALL    
exif.decode_jis_intel                 "JIS"                                           PHP_INI_ALL    从 PHP 4.3.0 起可用。
exif.decode_jis_motorola              "JIS"                                           PHP_INI_ALL    从 PHP 4.3.0 起可用。
exif.decode_unicode_intel             "UCS-2LE"                                       PHP_INI_ALL    从 PHP 4.3.0 起可用。
exif.decode_unicode_motorola          "UCS-2BE"                                       PHP_INI_ALL    从 PHP 4.3.0 起可用。
exif.encode_jis                       ""                                              PHP_INI_ALL    从 PHP 4.3.0 起可用。
exif.encode_unicode                   "ISO-8859-15"                                   PHP_INI_ALL    从 PHP 4.3.0 起可用。
exit_on_timeout                       ""                                              PHP_INI_ALL    从 PHP 5.3 起可用。0
expect.logfile                        ""                                              PHP_INI_ALL    
expect.loguser                        "1"                                             PHP_INI_ALL    
expect.timeout                        "10"                                            PHP_INI_ALL    
expose_php                            "1"                                             php.ini only
extension                             NULL                                            php.ini only
extension_dir                         "/path/to/php"                                  PHP_INI_SYSTEM
fastcgi.impersonate                   "0"                                             PHP_INI_SYSTEM 在 PHP <= 5.2.0 时是 PHP_INI_ALL    。 从 PHP 4.3.0 起可用。
fastcgi.logging                       "1"                                             PHP_INI_SYSTEM 在 PHP <= 5.2.0 时是 PHP_INI_ALL    。 从 PHP 4.4.0 起可用。
fbsql.allow_persistant                "1"                                             PHP_INI_SYSTEM 从 PHP 4.0.6 起可用。 在 PHP 4.2.0 中移除该选项。
fbsql.allow_persistent                "1"                                             PHP_INI_SYSTEM 从 PHP 4.2.0 起可用。
fbsql.autocommit                      "1"                                             PHP_INI_SYSTEM 从 PHP 4.0.6 起可用。
fbsql.batchSize                       "1000"                                          PHP_INI_SYSTEM 从 PHP 4.2.0 起可用。 在 PHP 5.1.0 中移除该选项。
fbsql.batchsize                       "1000"                                          PHP_INI_ALL    从 PHP 5.1.0 起可用。
fbsql.default_database                ""                                              PHP_INI_SYSTEM 从 PHP 4.0.6 起可用。
fbsql.default_database_password       ""                                              PHP_INI_SYSTEM 从 PHP 4.0.6 起可用。
fbsql.default_host                    NULL                                            PHP_INI_SYSTEM 从 PHP 4.0.6 起可用。
fbsql.default_password                ""                                              PHP_INI_SYSTEM 从 PHP 4.0.6 起可用。
fbsql.default_user                    "_SYSTEM"                                       PHP_INI_SYSTEM 从 PHP 4.0.6 起可用。
fbsql.generate_warnings               "0"                                             PHP_INI_SYSTEM 从 PHP 4.0.6 起可用。
fbsql.max_connections                 "128"                                           PHP_INI_SYSTEM 从 PHP 4.0.6 起可用。
fbsql.max_links                       "128"                                           PHP_INI_SYSTEM 从 PHP 4.0.6 起可用。
fbsql.max_persistent                  "-1"                                            PHP_INI_SYSTEM 从 PHP 4.0.6 起可用。
fbsql.max_results                     "128"                                           PHP_INI_SYSTEM 从 PHP 4.0.6 起可用。
fbsql.mbatchSize                      "1000"                                          PHP_INI_SYSTEM 从 PHP 4.0.6 起可用。 在 PHP 4.2.0 中移除该选项。
fbsql.show_timestamp_decimals         "0"                                             PHP_INI_SYSTEM 从 PHP 5.1.5 起可用。
file_uploads                          "1"                                             PHP_INI_SYSTEM 在 PHP <= 4.2.3 时是 PHP_INI_ALL    。 从 PHP 4.0.3 起可用。
filter.default                        "unsafe_raw"                                    PHP_INI_PERDIR 在 filter <= 0.9.4 时是 PHP_INI_ALL    。 从 PHP 5.2.0 起可用。
filter.default_flags                  NULL                                            PHP_INI_PERDIR 在 filter <= 0.9.4 时是 PHP_INI_ALL    。 从 PHP 5.2.0 起可用。
from                                  ""                                              PHP_INI_ALL    
gd.jpeg_ignore_warning                "0"                                             PHP_INI_ALL    从 PHP 5.1.3 起可用。
geoip.custom_directory                NULL                                            PHP_INI_ALL    从 geoip 1.0.1 起可用。
geoip.database_standard               "GeoIP.dat"                                     PHP_INI_ALL    在 geoip 1.0.1 中移除该选项。
gpc_order                             "GPC"                                           PHP_INI_ALL    在 PHP 5.0.0 中移除该选项。
hidef.ini_path                        (char*)default_ini_path                         PHP_INI_SYSTEM
highlight.bg                          "#FFFFFF"                                       PHP_INI_ALL    在 PHP 5.4.0 中移除该选项。
highlight.comment                     "#FF8000"                                       PHP_INI_ALL    
highlight.default                     "#0000BB"                                       PHP_INI_ALL    
highlight.html                        "#000000"                                       PHP_INI_ALL    
highlight.keyword                     "#007700"                                       PHP_INI_ALL    
highlight.string                      "#DD0000"                                       PHP_INI_ALL    
html_errors                           "1"                                             PHP_INI_ALL    在 PHP <= 4.2.3 时是 PHP_INI_SYSTEM。 从 PHP 4.0.2 起可用。
htscanner.config_file                 ".htaccess"                                     PHP_INI_SYSTEM
htscanner.default_docroot             "/"                                             PHP_INI_SYSTEM
htscanner.default_ttl                 "300"                                           PHP_INI_SYSTEM 从 htscanner 0.6.0 起可用。
htscanner.stop_on_error               "0"                                             PHP_INI_SYSTEM 从 htscanner 0.7.0 起可用。
http.allowed_methods                  ""                                              PHP_INI_ALL    Available since pecl_http 0.4.0. 在 pecl_http 1.0.0 中移除该选项。
http.allowed_methods_log              ""                                              PHP_INI_ALL    Available since pecl_http 0.12.0. 在 pecl_http 1.0.0 中移除该选项。
http.cache_log                        ""                                              PHP_INI_ALL    Available since pecl_http 0.8.0. 在 pecl_http 1.0.0 中移除该选项。
http.composite_log                    ""                                              PHP_INI_ALL    Available since pecl_http 0.12.0. 在 pecl_http 1.0.0 中移除该选项。
http.etag.mode                        "MD5"                                           PHP_INI_ALL    从 pecl_http 1.0.0 起可用。
http.etag_mode                        "MD5"                                           PHP_INI_ALL    Available since pecl_http 0.12.0. 在 pecl_http 1.0.0 中移除该选项。
http.force_exit                       "1"                                             PHP_INI_ALL    从 pecl_http 0.18.0 起可用。
http.log.allowed_methods              ""                                              PHP_INI_ALL    从 pecl_http 1.0.0 起可用。
http.log.cache                        ""                                              PHP_INI_ALL    从 pecl_http 1.0.0 起可用。
http.log.composite                    ""                                              PHP_INI_ALL    从 pecl_http 1.0.0 起可用。
http.log.not_found                    ""                                              PHP_INI_ALL    从 pecl_http 1.0.0 起可用。
http.log.redirect                     ""                                              PHP_INI_ALL    从 pecl_http 1.0.0 起可用。
http.ob_deflate_auto                  "0"                                             PHP_INI_PERDIR Available since pecl_http 0.21.0. 在 pecl_http 1.0.0 中移除该选项。
http.ob_deflate_flags                 "0"                                             PHP_INI_ALL    Available since pecl_http 0.21.0. 在 pecl_http 1.0.0 中移除该选项。
http.ob_inflate_auto                  "0"                                             PHP_INI_PERDIR Available since pecl_http 0.21.0. 在 pecl_http 1.0.0 中移除该选项。
http.ob_inflate_flags                 "0"                                             PHP_INI_ALL    Available since pecl_http 0.21.0. 在 pecl_http 1.0.0 中移除该选项。
http.only_exceptions                  "0"                                             PHP_INI_ALL    从 pecl_http 0.11.0 起可用。
http.persistent.handles.ident         "GLOBAL"                                        PHP_INI_ALL    从 pecl_http 1.5.0 起可用。
http.persistent.handles.limit         "-1"                                            PHP_INI_SYSTEM 从 pecl_http 1.5.0 起可用。
http.redirect_log                     ""                                              PHP_INI_ALL    Available since pecl_http 0.12.0. 在 pecl_http 1.0.0 中移除该选项。
http.request.datashare.connect        "0"                                             PHP_INI_SYSTEM 从 pecl_http 1.3.0 起可用。
http.request.datashare.cookie         "0"                                             PHP_INI_SYSTEM 从 pecl_http 1.3.0 起可用。
http.request.datashare.dns            "1"                                             PHP_INI_SYSTEM 从 pecl_http 1.3.0 起可用。
http.request.datashare.ssl            "0"                                             PHP_INI_SYSTEM 从 pecl_http 1.3.0 起可用。
http.request.methods.allowed          ""                                              PHP_INI_ALL    从 pecl_http 1.0.0 起可用。
http.request.methods.custom           ""                                              PHP_INI_PERDIR 从 pecl_http 1.0.0 起可用。
http.send.deflate.start_auto          "0"                                             PHP_INI_PERDIR 从 pecl_http 1.0.0 起可用。
http.send.deflate.start_flags         "0"                                             PHP_INI_ALL    从 pecl_http 1.0.0 起可用。
http.send.inflate.start_auto          "0"                                             PHP_INI_PERDIR 从 pecl_http 1.0.0 起可用。
http.send.inflate.start_flags         "0"                                             PHP_INI_ALL    从 pecl_http 1.0.0 起可用。
http.send.not_found_404               "1"                                             PHP_INI_ALL    从 pecl_http 1.0.0 起可用。
hyerwave.allow_persistent             "0"                                             PHP_INI_SYSTEM 在 PHP 4.3.2 中移除该选项。
hyperwave.allow_persistent            "0"                                             PHP_INI_SYSTEM 从 PHP 4.3.2 起可用。 在 PHP 5.0.0 中移除该选项。
hyperwave.default_port                "418"                                           PHP_INI_ALL    在 PHP 5.0.0 中移除该选项。
ibase.allow_persistent                "1"                                             PHP_INI_SYSTEM
ibase.dateformat                      "%Y-%m-%d"                                      PHP_INI_ALL    
ibase.default_charset                 NULL                                            PHP_INI_ALL    从 PHP 5.0.0 起可用。
ibase.default_db                      NULL                                            PHP_INI_SYSTEM 从 PHP 5.0.0 起可用。
ibase.default_password                NULL                                            PHP_INI_ALL    
ibase.default_user                    NULL                                            PHP_INI_ALL    
ibase.max_links                       "-1"                                            PHP_INI_SYSTEM
ibase.max_persistent                  "-1"                                            PHP_INI_SYSTEM
ibase.timeformat                      "%H:%M:%S"                                      PHP_INI_ALL    
ibase.timestampformat                 "%Y-%m-%d %H:%M:%S"                             PHP_INI_ALL    
ibm_db2.binmode                       "1"                                             PHP_INI_ALL    
ibm_db2.i5_allow_commit               "0"                                             PHP_INI_SYSTEM 从 ibm_db2 1.4.9 起可用。
ibm_db2.i5_dbcs_alloc                 "0"                                             PHP_INI_SYSTEM 从 ibm_db2 1.5.0 起可用。
ibm_db2.instance_name                 NULL                                            PHP_INI_SYSTEM 从 ibm_db2 1.0.2 起可用。
iconv.input_encoding                  "ISO-8859-1"                                    PHP_INI_ALL    从 PHP 4.0.5 起可用。
iconv.internal_encoding               "ISO-8859-1"                                    PHP_INI_ALL    从 PHP 4.0.5 起可用。
iconv.output_encoding                 "ISO-8859-1"                                    PHP_INI_ALL    从 PHP 4.0.5 起可用。
ifx.allow_persistent                  "1"                                             PHP_INI_SYSTEM 在 PHP 5.2.1 中移除该选项。
ifx.blobinfile                        "1"                                             PHP_INI_ALL    在 PHP 5.2.1 中移除该选项。
ifx.byteasvarchar                     "0"                                             PHP_INI_ALL    在 PHP 5.2.1 中移除该选项。
ifx.charasvarchar                     "0"                                             PHP_INI_ALL    在 PHP 5.2.1 中移除该选项。
ifx.default_host                      NULL                                            PHP_INI_SYSTEM 在 PHP 5.2.1 中移除该选项。
ifx.default_password                  NULL                                            PHP_INI_SYSTEM 在 PHP 5.2.1 中移除该选项。
ifx.default_user                      NULL                                            PHP_INI_SYSTEM 在 PHP 5.2.1 中移除该选项。
ifx.max_links                         "-1"                                            PHP_INI_SYSTEM 在 PHP 5.2.1 中移除该选项。
ifx.max_persistent                    "-1"                                            PHP_INI_SYSTEM 在 PHP 5.2.1 中移除该选项。
ifx.nullformat                        "0"                                             PHP_INI_ALL    在 PHP 5.2.1 中移除该选项。
ifx.textasvarchar                     "0"                                             PHP_INI_ALL    在 PHP 5.2.1 中移除该选项。
ignore_repeated_errors                "0"                                             PHP_INI_ALL    从 PHP 4.3.0 起可用。
ignore_repeated_source                "0"                                             PHP_INI_ALL    从 PHP 4.3.0 起可用。
ignore_user_abort                     "0"                                             PHP_INI_ALL    
imlib2.font_cache_max_size            "524288"                                        PHP_INI_ALL    
imlib2.font_path                      "/usr/share/php/fonts/"                         PHP_INI_ALL    
implicit_flush                        "0"                                             PHP_INI_ALL    在 PHP <= 4.2.3 时是 PHP_INI_PERDIR。
include_path                          ".;/path/to/php/pear"                           PHP_INI_ALL    
ingres.allow_persistent               "1"                                             PHP_INI_SYSTEM 从 PHP 4.0.2 起可用。 在 PHP 5.1.0 中移除该选项。
ingres.array_index_start              "1"                                             PHP_INI_ALL    从 ingres 1.4.0 起可用。
ingres.blob_segment_length            "4096"                                          PHP_INI_ALL    从 ingres 1.2.0 起可用。
ingres.cursor_mode                    "0"                                             PHP_INI_ALL    从 ingres 1.1 起可用。
ingres.default_database               NULL                                            PHP_INI_ALL    从 PHP 4.0.2 起可用。 在 PHP 5.1.0 中移除该选项。
ingres.default_password               NULL                                            PHP_INI_ALL    从 PHP 4.0.2 起可用。 在 PHP 5.1.0 中移除该选项。
ingres.default_user                   NULL                                            PHP_INI_ALL    从 PHP 4.0.2 起可用。 在 PHP 5.1.0 中移除该选项。
ingres.max_links                      "-1"                                            PHP_INI_SYSTEM 从 PHP 4.0.2 起可用。 在 PHP 5.1.0 中移除该选项。
ingres.max_persistent                 "-1"                                            PHP_INI_SYSTEM 从 PHP 4.0.2 起可用。 在 PHP 5.1.0 中移除该选项。
ingres.report_db_warnings             "1"                                             PHP_INI_ALL    从 ingres 1.1 起可用。
ingres.timeout                        "-1"                                            PHP_INI_ALL    从 ingres 1.4.0 起可用。
ingres.trace_connect                  "0"                                             PHP_INI_ALL    从 ingres 1.2.1 起可用。
ircg.control_user                     "nobody"                                        PHP_INI_ALL    从 PHP 5.0.0 起可用。 在 PHP 5.1.0 中移除该选项。
ircg.keep_alive_interval              "60"                                            PHP_INI_ALL    从 PHP 5.0.0 起可用。 在 PHP 5.1.0 中移除该选项。
ircg.max_format_message_sets          "12"                                            PHP_INI_ALL    从 PHP 5.0.0 起可用。 在 PHP 5.1.0 中移除该选项。
ircg.shared_mem_size                  "6000000"                                       PHP_INI_ALL    从 PHP 5.0.0 起可用。 在 PHP 5.1.0 中移除该选项。
ircg.work_dir                         "/tmp/ircg"                                     PHP_INI_ALL    从 PHP 5.0.0 起可用。 在 PHP 5.1.0 中移除该选项。
last_modified                         "0"                                             PHP_INI_ALL    从 PHP 4.0.5 起可用。
ldap.base_dn                          NULL                                            PHP_INI_ALL    在 PHP 4.2.0 中移除该选项。
ldap.max_links                        ""                                              PHP_INI_SYSTEM
log.dbm_dir                           ""                                              PHP_INI_ALL    在 PHP 4.0.1 中移除该选项。
log_errors                            "0"                                             PHP_INI_ALL    
log_errors_max_len                    "1024"                                          PHP_INI_ALL    从 PHP 4.3.0 起可用。
magic_quotes_gpc                      "1"                                             PHP_INI_PERDIR 在 PHP <= 4.2.3 时是 PHP_INI_ALL    。 从 PHP 5.3.0 起不推荐使用。 在 PHP 5.4.0 中移除该选项。
magic_quotes_runtime                  "0"                                             PHP_INI_ALL    在 PHP 5.4.0 中移除该选项。
magic_quotes_sybase                   "0"                                             PHP_INI_ALL    在 PHP 5.4.0 中移除该选项。
mail.add_x_header                     "0"                                             PHP_INI_PERDIR 从 PHP 5.3.0 起可用。
mail.force_extra_parameters           NULL                                            php.ini only   从 PHP 5.0.0 起可用。
mail.log                              ""                                              PHP_INI_ALL    从 PHP 5.3.0 起可用。
mailparse.def_charset                 "us-ascii"                                      PHP_INI_ALL    从 PHP 4.1.0 起可用。 在 PHP 4.2.0 中移除该选项。
maxdb.default_db                      NULL                                            PHP_INI_ALL    
maxdb.default_host                    NULL                                            PHP_INI_ALL    
maxdb.default_pw                      NULL                                            PHP_INI_ALL    
maxdb.default_user                    NULL                                            PHP_INI_ALL    
maxdb.long_readlen                    "200"                                           PHP_INI_ALL    
max_execution_time                    "30"                                            PHP_INI_ALL    
max_input_nesting_level               "64"                                            PHP_INI_PERDIR 从 PHP 4.4 起可用。8 and PHP 5.2.3.
max_input_vars                        1000                                            PHP_INI_PERDIR 从 PHP 5.3.9 起可用。
max_input_time                        ""                                              PHP_INI_PERDIR 从 PHP 4.3.0 起可用。
mbstring.detect_order                 NULL                                            PHP_INI_ALL    从 PHP 4.0.6 起可用。
mbstring.encoding_translation         "0"                                             PHP_INI_PERDIR 从 PHP 4.3.0 起可用。
mbstring.func_overload                "0"                                             PHP_INI_SYSTEM 在 PHP <= 4.2.3 时是 PHP_INI_SYSTEM；从 PHP 4.3 起可用于 PHP_INI_SYSTEM | PHP_INI_PERDIR 。 through 5.2.6.      从 PHP 4.2.0 起可用。
mbstring.http_input                   "pass"                                          PHP_INI_ALL    从 PHP 4.0.6 起可用。
mbstring.http_output                  "pass"                                          PHP_INI_ALL    从 PHP 4.0.6 起可用。
mbstring.internal_encoding            NULL                                            PHP_INI_ALL    从 PHP 4.0.6 起可用。
mbstring.language                     "neutral"                                       PHP_INI_ALL     从 PHP 4.3.0 起可用；在 PHP <= 5.2.6 时是 PHP_INI_PERDIR 。
mbstring.script_encoding              NULL                                            PHP_INI_ALL    从 PHP 4.3.0 起可用。
mbstring.strict_detection             "0"                                             PHP_INI_ALL    从 PHP 5.1.2 起可用。
mbstring.substitute_character         NULL                                            PHP_INI_ALL    从 PHP 4.0.6 起可用。
mcrypt.algorithms_dir                 NULL                                            PHP_INI_ALL    从 PHP 4.0.2 起可用。
mcrypt.modes_dir                      NULL                                            PHP_INI_ALL    从 PHP 4.0.2 起可用。
memcache.allow_failover               "1"                                             PHP_INI_ALL    从 memcache 2.0.2 起可用。
memcache.chunk_size                   "8192"                                          PHP_INI_ALL    从 memcache 2.0.2 起可用。
memcache.default_port                 "11211"                                         PHP_INI_ALL    从 memcache 2.0.2 起可用。
memcache.hash_function                "crc32"                                         PHP_INI_ALL    从 memcache 2.2.0 起可用。
memcache.hash_strategy                "standard"                                      PHP_INI_ALL    从 memcache 2.2.0 起可用。
memcache.max_failover_attempts        "20"                                            PHP_INI_ALL    从 memcache 2.1.0 起可用。
memory_limit                          "128M"                                          PHP_INI_ALL    
mime_magic.debug                      "0"                                             PHP_INI_SYSTEM 从 PHP 5.0.0 起可用。
mime_magic.magicfile                  "/path/to/php/magic.mime"                       PHP_INI_SYSTEM 从 PHP 4.3.0 起可用。
msql.allow_persistent                 "1"                                             PHP_INI_ALL    
msql.max_links                        ""                                              PHP_INI_ALL    
msql.max_persistent                   ""                                              PHP_INI_ALL    
mssql.allow_persistent                "1"                                             PHP_INI_SYSTEM
mssql.batchsize                       "0"                                             PHP_INI_ALL    从 PHP 4.0.4 起可用。
mssql.charset                         ""                                              PHP_INI_ALL    从 PHP 5.1.2 起可用。
mssql.compatability_mode              "0"                                             PHP_INI_ALL    
mssql.connect_timeout                 "5"                                             PHP_INI_ALL    
mssql.datetimeconvert                 "1"                                             PHP_INI_ALL    从 PHP 4.2.0 起可用。
mssql.max_links                       ""                                              PHP_INI_SYSTEM
mssql.max_persistent                  ""                                              PHP_INI_SYSTEM
mssql.max_procs                       ""                                              PHP_INI_ALL    从 PHP 4.3.0 起可用。
mssql.min_error_severity              "10"                                            PHP_INI_ALL    
mssql.min_message_severity            "10"                                            PHP_INI_ALL    
mssql.secure_connection               "0"                                             PHP_INI_SYSTEM 从 PHP 4.3.0 起可用。
mssql.textlimit                       ""                                              PHP_INI_ALL    
mssql.textsize                        ""                                              PHP_INI_ALL    
mssql.timeout                         "60"                                            PHP_INI_ALL    从 PHP 4.1.0 起可用。
mysql.allow_persistent                "1"                                             PHP_INI_SYSTEM
mysql.connect_timeout                 "60"                                            PHP_INI_ALL    在 PHP <= 4.3.2 时是 PHP_INI_SYSTEM。 从 PHP 4.3.0 起可用。
mysql.default_host                    NULL                                            PHP_INI_ALL    
mysql.default_password                NULL                                            PHP_INI_ALL    
mysql.default_port                    NULL                                            PHP_INI_ALL    
mysql.default_socket                  NULL                                            PHP_INI_ALL    从 PHP 4.0.1 起可用。
mysql.default_user                    NULL                                            PHP_INI_ALL    
mysql.max_links                       ""                                              PHP_INI_SYSTEM
mysql.max_persistent                  ""                                              PHP_INI_SYSTEM
mysql.trace_mode                      "0"                                             PHP_INI_ALL    从 PHP 4.3.0 起可用。
mysqli.default_host                   NULL                                            PHP_INI_ALL    从 PHP 5.0.0 起可用。
mysqli.default_port                   "3306"                                          PHP_INI_ALL    从 PHP 5.0.0 起可用。
mysqli.default_pw                     NULL                                            PHP_INI_ALL    从 PHP 5.0.0 起可用。
mysqli.default_socket                 NULL                                            PHP_INI_ALL    从 PHP 5.0.0 起可用。
mysqli.default_user                   NULL                                            PHP_INI_ALL    从 PHP 5.0.0 起可用。
mysqli.max_links                      ""                                              PHP_INI_SYSTEM 从 PHP 5.0.0 起可用。
mysqli.reconnect                      "0"                                             PHP_INI_SYSTEM 从 PHP 5.0.0 起可用。
namazu.debugmode                      "0"                                             PHP_INI_ALL    
namazu.lang                           NULL                                            PHP_INI_ALL    
namazu.loggingmode                    "0"                                             PHP_INI_ALL    
namazu.sortmethod                     NULL                                            PHP_INI_ALL    
namazu.sortorder                      NULL                                            PHP_INI_ALL    
nsapi.read_timeout                    "60"                                            PHP_INI_ALL    从 PHP 4.3.3 起可用。
oci8.default_prefetch                 "10"                                            PHP_INI_SYSTEM 从 PHP 5.1.2 起可用。
oci8.max_persistent                   ""                                              PHP_INI_SYSTEM 从 PHP 5.1.2 起可用。
oci8.old_oci_close_semantics          "0"                                             PHP_INI_SYSTEM 从 PHP 5.1.2 起可用。
oci8.persistent_timeout               ""                                              PHP_INI_SYSTEM 从 PHP 5.1.2 起可用。
oci8.ping_interval                    "60"                                            PHP_INI_SYSTEM 从 PHP 5.1.2 起可用。
oci8.privileged_connect               "0"                                             PHP_INI_SYSTEM 从 PHP 5.1.2 起可用。
oci8.statement_cache_size             "20"                                            PHP_INI_SYSTEM 从 PHP 5.1.2 起可用。
odbc.allow_persistent                 "1"                                             PHP_INI_SYSTEM
odbc.check_persistent                 "1"                                             PHP_INI_SYSTEM
odbc.defaultbinmode                   "1"                                             PHP_INI_ALL    
odbc.defaultlrl                       "4096"                                          PHP_INI_ALL    
odbc.default_db                       NULL                                            PHP_INI_ALL    
odbc.default_pw                       NULL                                            PHP_INI_ALL    
odbc.default_user                     NULL                                            PHP_INI_ALL    
odbc.max_links                        ""                                              PHP_INI_SYSTEM
odbc.max_persistent                   ""                                              PHP_INI_SYSTEM
odbtp.datetime_format                 "object"                                        PHP_INI_ALL    
odbtp.detach_default_queries          "0"                                             PHP_INI_ALL    
odbtp.guid_format                     "string"                                        PHP_INI_ALL    从 odbtp 1.1.3 起可用。
odbtp.interface_file                  "/usr/local/share/odbtp.conf"                      PHP_INI_ALL    
odbtp.truncation_errors               "1"                                             PHP_INI_ALL    
opendirectory.default_separator       "/"                                             PHP_INI_ALL    在 opendirectory 0.2.2 中移除该选项。
opendirectory.max_refs                ""                                              PHP_INI_ALL    
opendirectory.separator               "/"                                             PHP_INI_ALL    从 opendirectory 0.2.2 起可用。
open_basedir                          NULL                                            PHP_INI_ALL    在 PHP < 5.2.3 时是 PHP_INI_SYSTEM。
oracle.allow_persistent               ""                                              PHP_INI_ALL    在 PHP 5.1.0 中移除该选项。
oracle.max_links                      ""                                              PHP_INI_ALL    在 PHP 5.1.0 中移除该选项。
oracle.max_persistent                 ""                                              PHP_INI_ALL    在 PHP 5.1.0 中移除该选项。
output_buffering                      "0"                                             PHP_INI_PERDIR
output_handler                        NULL                                            PHP_INI_PERDIR 从 PHP 4.0.4 起可用。
pam.servicename                       "php"                                           PHP_INI_ALL    
pcre.backtrack_limit                  "1000000"                                       PHP_INI_ALL    从 PHP 5.2.0 起可用。
pcre.recursion_limit                  "100000"                                        PHP_INI_ALL    从 PHP 5.2.0 起可用。
pdo.dsn.*                                                                             php.ini only   从 PHP 5.1.0 起可用。
pdo_odbc.connection_pooling           "strict"                                        PHP_INI_ALL    从 PHP 5.1.0 起可用。
pdo_odbc.db2_instance_name            NULL                                            PHP_INI_SYSTEM 从 PHP 5.1.1 起可用。 此已废弃的 特性即将 被移除。
pfpro.defaulthost                     "test-payflow.verisign.com"                      PHP_INI_ALL    从 PHP 4.0.2 起可用。 在 PHP 5.1.0 中移除该选项。
pfpro.defaultport                     "443"                                           PHP_INI_ALL    从 PHP 4.0.2 起可用。 在 PHP 5.1.0 中移除该选项。
pfpro.defaulttimeout                  "30"                                            PHP_INI_ALL    从 PHP 4.0.2 起可用。 在 PHP 5.1.0 中移除该选项。
pfpro.proxyaddress                    ""                                              PHP_INI_ALL    从 PHP 4.0.2 起可用。 在 PHP 5.1.0 中移除该选项。
pfpro.proxylogon                      ""                                              PHP_INI_ALL    从 PHP 4.0.2 起可用。 在 PHP 5.1.0 中移除该选项。
pfpro.proxypassword                   ""                                              PHP_INI_ALL    从 PHP 4.0.2 起可用。 在 PHP 5.1.0 中移除该选项。
pfpro.proxyport                       ""                                              PHP_INI_ALL    从 PHP 4.0.2 起可用。 在 PHP 5.1.0 中移除该选项。
pgsql.allow_persistent                "1"                                             PHP_INI_SYSTEM
pgsql.auto_reset_persistent           "0"                                             PHP_INI_SYSTEM 从 PHP 4.2.0 起可用。
pgsql.ignore_notice                   "0"                                             PHP_INI_ALL    从 PHP 4.3.0 起可用。
pgsql.log_notice                      "0"                                             PHP_INI_ALL    从 PHP 4.3.0 起可用。
pgsql.max_links                       ""                                              PHP_INI_SYSTEM
pgsql.max_persistent                  ""                                              PHP_INI_SYSTEM
phar.extract_list                     ""                                              PHP_INI_ALL    从 phar 1.1.0 起可用。
phar.readonly                         "1"                                             PHP_INI_ALL    
phar.require_hash                     "1"                                             PHP_INI_ALL    
enable_post_data_reading              On                                              PHP_INI_PERDIR 从 PHP 5.4.0 起可用。
post_max_size                         "8M"                                            PHP_INI_PERDIR 在 PHP <= 4.2.3 时是 PHP_INI_SYSTEM。 从 PHP 4.0.3 起可用。
precision                             "14"                                            PHP_INI_ALL    
printer.default_printer               ""                                              PHP_INI_ALL    从 PHP 4.0.6 起可用。 在 PHP 4.1.1 中移除该选项。
python.append_path                    ""                                              PHP_INI_ALL    
python.prepend_path                   "."                                             PHP_INI_ALL    
realpath_cache_size                   "16K"                                           PHP_INI_SYSTEM 从 PHP 5.1.0 起可用。
realpath_cache_ttl                    "120"                                           PHP_INI_SYSTEM 从 PHP 5.1.0 起可用。
register_argc_argv                    "1"                                             PHP_INI_PERDIR 在 PHP <= 4.2.3 时是 PHP_INI_ALL    。
register_globals                      "0"                                             PHP_INI_PERDIR 在 PHP <= 4.2.3 时是 PHP_INI_ALL    。 从 PHP 5.3.0 起不推荐使用。 在 PHP 5.4.0 中移除该选项。
register_long_arrays                  "1"                                             PHP_INI_PERDIR 从 PHP 5.0.0 起可用。 从 PHP 5.3.0 起不推荐使用。在 PHP 5.4.0 中移除该选项。
report_memleaks                       "1"                                             PHP_INI_ALL    从 PHP 4.3.0 起可用。
report_zend_debug                     "1"                                             PHP_INI_ALL    从 PHP 5.0.0 起可用。
request_order                         ""                                              PHP_INI_PERDIR 在 PHP 5.3.0 时增加
runkit.internal_override              "0"                                             PHP_INI_SYSTEM
runkit.superglobal                    ""                                              PHP_INI_PERDIR
safe_mode                             "0"                                             PHP_INI_SYSTEM 在 PHP 5.4.0 中移除该选项。
safe_mode_allowed_env_vars            "PHP_"                                          PHP_INI_SYSTEM 在 PHP 5.4.0 中移除该选项。
safe_mode_exec_dir                    ""                                              PHP_INI_SYSTEM 在 PHP 5.4.0 中移除该选项。
safe_mode_gid                         "0"                                             PHP_INI_SYSTEM 从 PHP 4.1.0 起可用。 在 PHP 5.4.0 中移除该选项。
safe_mode_include_dir                 NULL                                            PHP_INI_SYSTEM 从 PHP 4.1.0 起可用。 在 PHP 5.4.0 中移除该选项。
safe_mode_protected_env_vars          "LD_LIBRARY_PATH"                               PHP_INI_SYSTEM 在 PHP 5.4.0 中移除该选项。
sendmail_from                         NULL                                            PHP_INI_ALL    
sendmail_path                         "/usr/sbin/sendmail -t -i"                      PHP_INI_SYSTEM
serialize_precision                   "17"                                            PHP_INI_ALL     从 PHP 4.3.2 起可用。 Until PHP 5.3.5, the default value was 100.
session.auto_start                    "0"                                             PHP_INI_ALL    
session.bug_compat_42                 "1"                                             PHP_INI_ALL    从 PHP 4.3.0 起可用。 在 PHP 5.4.0 中移除该选项。
session.bug_compat_warn               "1"                                             PHP_INI_ALL    从 PHP 4.3.0 起可用。 在 PHP 5.4.0 中移除该选项。
session.cache_expire                  "180"                                           PHP_INI_ALL    
session.cache_limiter                 "nocache"                                       PHP_INI_ALL    
session.cookie_domain                 ""                                              PHP_INI_ALL    
session.cookie_httponly               ""                                              PHP_INI_ALL    从 PHP 5.2.0 起可用。
session.cookie_lifetime               "0"                                             PHP_INI_ALL    
session.cookie_path                   "/"                                             PHP_INI_ALL    
session.cookie_secure                 ""                                              PHP_INI_ALL    从 PHP 4.0.4 起可用。
session.entropy_file                  ""                                              PHP_INI_ALL    
session.entropy_length                "0"                                             PHP_INI_ALL    
session.gc_dividend                   "100"                                           PHP_INI_ALL    从 PHP 4.3.0 起可用。 在 PHP 4.3.2 中移除该选项。
session.gc_divisor                    "100"                                           PHP_INI_ALL    从 PHP 4.3.2 起可用。
session.gc_maxlifetime                "1440"                                          PHP_INI_ALL    
session.gc_probability                "1"                                             PHP_INI_ALL    
session.hash_bits_per_character       "4"                                             PHP_INI_ALL    从 PHP 5.0.0 起可用。
session.hash_function                 "0"                                             PHP_INI_ALL    从 PHP 5.0.0 起可用。
session.name                          "PHPSESSID"                                     PHP_INI_ALL    
session.referer_check                 ""                                              PHP_INI_ALL    
session.save_handler                  "files"                                         PHP_INI_ALL    
session.save_path                     ""                                              PHP_INI_ALL    
session.serialize_handler             "php"                                           PHP_INI_ALL    
session.use_cookies                   "1"                                             PHP_INI_ALL    
session.use_only_cookies              "1"                                             PHP_INI_ALL    从 PHP 4.3.0 起可用。
session.use_trans_sid                 "0"                                             PHP_INI_ALL    在 PHP <= 4.2.3 时是 PHP_INI_ALL    。 在 PHP < 5 时是 PHP_INI_PERDIR。 从 PHP 4.0.3 起可用。
session_pgsql.create_table            "1"                                             PHP_INI_SYSTEM
session_pgsql.db                      "host=localhost dbname=php_session user=nobody" PHP_INI_SYSTEM
session_pgsql.disable                 "0"                                             PHP_INI_SYSTEM
session_pgsql.failover_mode           "0"                                             PHP_INI_SYSTEM
session_pgsql.gc_interval             "3600"                                          PHP_INI_SYSTEM
session_pgsql.keep_expired            "0"                                             PHP_INI_SYSTEM
session_pgsql.sem_file_name           "/tmp/php_session_pgsql"                        PHP_INI_SYSTEM
session_pgsql.serializable            "0"                                             PHP_INI_SYSTEM
session_pgsql.short_circuit           "0"                                             PHP_INI_SYSTEM
session_pgsql.use_app_vars            "0"                                             PHP_INI_SYSTEM
session_pgsql.vacuum_interval         "21600"                                         PHP_INI_SYSTEM
short_open_tag                        "1"                                             PHP_INI_ALL     在 PHP 4.0.0 时是 PHP_INI_ALL    。 在 PHP < 5.3.0 时是 PHP_INI_PERDIR
simple_cvs.authMethod                 "0"                                             PHP_INI_ALL    
simple_cvs.compressionLevel           "0"                                             PHP_INI_ALL    
simple_cvs.cvsRoot                    "0"                                             PHP_INI_ALL    
simple_cvs.host                       "0"                                             PHP_INI_ALL    
simple_cvs.moduleName                 "0"                                             PHP_INI_ALL    
simple_cvs.userName                   "0"                                             PHP_INI_ALL    
simple_cvs.workingDir                 "0"                                             PHP_INI_ALL    
SMTP                                  "localhost"                                     PHP_INI_ALL    
smtp_port                             "25"                                            PHP_INI_ALL    从 PHP 4.3.0 起可用。
soap.wsdl_cache                       "1"                                             PHP_INI_ALL    从 PHP 5.1.5 起可用。
soap.wsdl_cache_dir                   "/tmp"                                          PHP_INI_ALL    从 PHP 5.0.0 起可用。
soap.wsdl_cache_enabled               "1"                                             PHP_INI_ALL    从 PHP 5.0.0 起可用。
soap.wsdl_cache_limit                 "5"                                             PHP_INI_ALL    从 PHP 5.1.5 起可用。
soap.wsdl_cache_ttl                   "86400"                                         PHP_INI_ALL    从 PHP 5.0.0 起可用。
sql.safe_mode                         "0"                                             PHP_INI_SYSTEM
sqlite.assoc_case                     "0"                                             PHP_INI_ALL    从 PHP 5.0.0 起可用。
sybase.allow_persistent               "1"                                             PHP_INI_ALL    在 PHP <= 4.0.2 时是 PHP_INI_ALL    。 在 PHP <= 4.0.3 时是 PHP_INI_SYSTEM。
sybase.hostname                       NULL                                            PHP_INI_ALL    在 PHP 4.0.2 中移除该选项。
sybase.interface_file                 ""                                              PHP_INI_ALL    
sybase.login_timeout                  "0"                                             PHP_INI_ALL    在 PHP 4.0.2 中移除该选项。
sybase.max_links                      ""                                              PHP_INI_ALL    在 PHP <= 4.0.2 时是 PHP_INI_ALL    。 在 PHP <= 4.0.3 时是 PHP_INI_SYSTEM。
sybase.max_persistent                 ""                                              PHP_INI_ALL    在 PHP <= 4.0.2 时是 PHP_INI_ALL    。 在 PHP <= 4.0.3 时是 PHP_INI_SYSTEM。
sybase.min_client_severity            "10"                                            PHP_INI_ALL    在 PHP 4.0.2 中移除该选项。
sybase.min_error_severity             "10"                                            PHP_INI_ALL    
sybase.min_message_severity           "10"                                            PHP_INI_ALL    
sybase.min_server_severity            "10"                                            PHP_INI_ALL    在 PHP 4.0.2 中移除该选项。
sybase.timeout                        "0"                                             PHP_INI_ALL    在 PHP 4.0.2 中移除该选项。
sybct.allow_persistent                "1"                                             PHP_INI_SYSTEM 在 PHP <= 4.0.2 时是 PHP_INI_ALL    。 从 PHP 4.0.2 起可用。 在 PHP 4.0.3 中移除该选项。
sybct.deadlock_retry_count            "0"                                             PHP_INI_ALL    从 PHP 4.3.0 起可用。
sybct.hostname                        NULL                                            PHP_INI_ALL    从 PHP 4.0.2 起可用。 在 PHP 4.0.3 中移除该选项。
sybct.login_timeout                   ""                                              PHP_INI_ALL    从 PHP 4.0.2 起可用。
sybct.max_links                       ""                                              PHP_INI_SYSTEM 在 PHP <= 4.0.2 时是 PHP_INI_ALL    。 从 PHP 4.0.2 起可用。 在 PHP 4.0.3 中移除该选项。
sybct.max_persistent                  ""                                              PHP_INI_SYSTEM 在 PHP <= 4.0.2 时是 PHP_INI_ALL    。 从 PHP 4.0.2 起可用。 在 PHP 4.0.3 中移除该选项。
sybct.min_client_severity             "10"                                            PHP_INI_ALL    从 PHP 4.0.2 起可用。 在 PHP 4.0.3 中移除该选项。
sybct.min_server_severity             "10"                                            PHP_INI_ALL    从 PHP 4.0.2 起可用。 在 PHP 4.0.3 中移除该选项。
sybct.packet_size                     "0"                                             PHP_INI_ALL    从 PHP 4.3.5 起可用。
sybct.timeout                         "0"                                             PHP_INI_ALL    从 PHP 4.0.2 起可用。
sysvshm.init_mem                      "10000"                                         PHP_INI_ALL    
tidy.clean_output                     "0"                                             php.ini only   在 PHP 5 时是 PHP_INI_PERDIR。 从 PHP 5.0.0 起可用。
tidy.default_config                   ""                                              PHP_INI_SYSTEM 从 PHP 5.0.0 起可用。
track_errors                          "0"                                             PHP_INI_ALL    
track_vars                            "1"                                             PHP_INI_ALL    在 PHP 4.0.3 中移除该选项。
unserialize_callback_func             NULL                                            PHP_INI_ALL    从 PHP 4.2.0 起可用。
uploadprogress.file.filename_template "/tmp/upt_%s.txt"                               PHP_INI_ALL    
upload_max_filesize                   "2M"                                            PHP_INI_PERDIR 在 PHP <= 4.2.3 时是 PHP_INI_ALL    。
max_file_uploads                      20                                              PHP_INI_SYSTEM 从 PHP 5.2.12 起可用。
upload_tmp_dir                        NULL                                            PHP_INI_SYSTEM
url_rewriter.tags                     "a=href,area=href,frame=src,form=,fieldset="                      PHP_INI_ALL    从 PHP 4.0.4 起可用。
user_agent                            NULL                                            PHP_INI_ALL    从 PHP 4.3.0 起可用。
user_dir                              NULL                                            PHP_INI_SYSTEM
user_ini.cache_ttl                    "300"                                           PHP_INI_SYSTEM 从 PHP 5.3.0 起可用。
user_ini.filename                     ".user.ini"                                     PHP_INI_SYSTEM 从 PHP 5.3.0 起可用。
valkyrie.auto_validate                "0"                                             PHP_INI_ALL    
valkyrie.config_path                  NULL                                            PHP_INI_ALL    
variables_order                       "EGPCS"                                         PHP_INI_PERDIR 在 PHP <= 5.0.5 时是 PHP_INI_ALL    。
velocis.max_links                     ""                                              PHP_INI_ALL    在 PHP 4.2.0 中移除该选项。
vld.active                            "0"                                             PHP_INI_SYSTEM
vld.execute                           "1"                                             PHP_INI_SYSTEM 从 vld 0.8.0 起可用。
vld.skip_append                       "0"                                             PHP_INI_SYSTEM 从 vld 0.8.0 起可用。
vld.skip_prepend                      "0"                                             PHP_INI_SYSTEM 从 vld 0.8.0 起可用。
windows_show_crt_warning              "0"                                             PHP_INI_ALL    从 PHP 5.4.0 起可用。
xbithack                              "0"                                             PHP_INI_ALL    从 PHP 4.0.5 起可用。
xdebug.auto_profile                   "0"                                             PHP_INI_ALL    在 Xdebug 2.0.0 中移除该选项。
xdebug.auto_profile_mode              "0"                                             PHP_INI_ALL    在 Xdebug 2.0.0 中移除该选项。
xdebug.auto_trace                     "0"                                             PHP_INI_ALL    
xdebug.collect_includes               "1"                                             PHP_INI_ALL    从 Xdebug 2.0.0 起可用。
xdebug.collect_params                 "0"                                             PHP_INI_ALL    
xdebug.collect_return                 "0"                                             PHP_INI_ALL    从 Xdebug 2.0.0 起可用。
xdebug.collect_vars                   "0"                                             PHP_INI_ALL    从 Xdebug 2.0.0 起可用。
xdebug.default_enable                 "1"                                             PHP_INI_ALL    在 Xdebug 1 时是 PHP_INI_SYSTEM。
xdebug.dump.COOKIE                    NULL                                            PHP_INI_ALL    
xdebug.dump.ENV                       NULL                                            PHP_INI_ALL    
xdebug.dump.FILES                     NULL                                            PHP_INI_ALL    
xdebug.dump.GET                       NULL                                            PHP_INI_ALL    
xdebug.dump.POST                      NULL                                            PHP_INI_ALL    
xdebug.dump.REQUEST                   NULL                                            PHP_INI_ALL    
xdebug.dump.SERVER                    NULL                                            PHP_INI_ALL    
xdebug.dump.SESSION                   NULL                                            PHP_INI_ALL    
xdebug.dump_globals                   "1"                                             PHP_INI_ALL    从 Xdebug 2.0.0 起可用。
xdebug.dump_once                      "1"                                             PHP_INI_ALL    
xdebug.dump_undefined                 "0"                                             PHP_INI_ALL    
xdebug.extended_info                  "1"                                             PHP_INI_SYSTEM 从 Xdebug 2.0.0 起可用。
xdebug.idekey                         ""                                              PHP_INI_ALL    从 Xdebug 2.0.0 起可用。
xdebug.manual_url                     "http://www.php.net"                            PHP_INI_ALL    
xdebug.max_nesting_level              "100"                                           PHP_INI_ALL    
xdebug.output_dir                     "/tmp"                                          PHP_INI_PERDIR 在 Xdebug <= 1.2.0 时是 PHP_INI_SYSTEM。 在 Xdebug 2.0.0 中移除该选项。
xdebug.profiler_aggregate             "0"                                             PHP_INI_PERDIR 从 Xdebug 2.0.0 起可用。
xdebug.profiler_append                "0"                                             PHP_INI_PERDIR 从 Xdebug 2.0.0 起可用。
xdebug.profiler_enable                "0"                                             PHP_INI_PERDIR 从 Xdebug 2.0.0 起可用。
xdebug.profiler_enable_trigger        "0"                                             PHP_INI_PERDIR 从 Xdebug 2.0.0 起可用。
xdebug.profiler_output_dir            "/tmp"                                          PHP_INI_PERDIR 从 Xdebug 2.0.0 起可用。
xdebug.profiler_output_name           "cachegrind.out.%p"                             PHP_INI_PERDIR 从 Xdebug 2.0.0 起可用。
xdebug.remote_autostart               "0"                                             PHP_INI_ALL    从 Xdebug 2.0.0 起可用。
xdebug.remote_enable                  "0"                                             PHP_INI_PERDIR
xdebug.remote_handler                 "dbgp"                                          PHP_INI_ALL    
xdebug.remote_host                    "localhost"                                     PHP_INI_ALL    
xdebug.remote_log                     ""                                              PHP_INI_ALL    从 Xdebug 2.0.0 起可用。
xdebug.remote_mode                    "req"                                           PHP_INI_ALL    
xdebug.remote_port                    "9000"                                          PHP_INI_ALL    
xdebug.show_exception_trace           "0"                                             PHP_INI_ALL    从 Xdebug 2.0.0 起可用。
xdebug.show_local_vars                "0"                                             PHP_INI_ALL    从 Xdebug 2.0.0 起可用。
xdebug.show_mem_delta                 "0"                                             PHP_INI_ALL    从 Xdebug 2.0.0 起可用。
xdebug.trace_format                   "0"                                             PHP_INI_ALL    从 Xdebug 2.0.0 起可用。
xdebug.trace_options                  "0"                                             PHP_INI_ALL    从 Xdebug 2.0.0 起可用。
xdebug.trace_output_dir               "/tmp"                                          PHP_INI_ALL    从 Xdebug 2.0.0 起可用。
xdebug.trace_output_name              "trace.%c"                                      PHP_INI_ALL    从 Xdebug 2.0.0 起可用。
xdebug.var_display_max_children       "128"                                           PHP_INI_ALL    从 Xdebug 2.0.0 起可用。
xdebug.var_display_max_data           "512"                                           PHP_INI_ALL    从 Xdebug 2.0.0 起可用。
xdebug.var_display_max_depth          "3"                                             PHP_INI_ALL    从 Xdebug 2.0.0 起可用。
xmlrpc_errors                         "0"                                             PHP_INI_SYSTEM 从 PHP 4.1.0 起可用。
xmlrpc_error_number                   "0"                                             PHP_INI_ALL    从 PHP 4.1.0 起可用。
xmms.path                             "/usr/bin/xmms"                                 PHP_INI_ALL    
xmms.session                          "0"                                             PHP_INI_ALL    
y2k_compliance                        "1"                                             PHP_INI_ALL    在 PHP 5.4.0 中移除该选项。
yami.response.timeout                 "5"                                             PHP_INI_ALL    从 yami 1.0.1 起可用。
yaz.keepalive                         "120"                                           PHP_INI_ALL    
yaz.log_file                          NULL                                            PHP_INI_ALL    从 PHP 4.3.0 起可用。 在 PHP 5.0.0 中移除该选项。
yaz.log_mask                          NULL                                            PHP_INI_ALL    从 yaz 1.0.3 起可用。
yaz.max_links                         "100"                                           PHP_INI_ALL    从 PHP 4.3.0 起可用。 在 PHP 5.0.0 中移除该选项。
zend.enable_gc                        "1"                                             PHP_INI_ALL    从 PHP 5.3.0 起可用。
zend.multibyte                        "0"                                             PHP_INI_PERDIR 从 PHP 5.4.0 起可用。
zend.script_encoding                  NULL                                            PHP_INI_ALL    从 PHP 5.4 起可用。0
zend.signal_check                     "0"                                             PHP_INI_SYSTEM 从 PHP 5.4 起可用。0
zend.ze1_compatibility_mode           "0"                                             PHP_INI_ALL    从 PHP 5.0.0 起可用。 在 PHP 5.3.0 中移除该选项。
zend_extension                        NULL                                            php.ini only
zend_extension_debug                  NULL                                            php.ini only
zend_extension_debug_ts               NULL                                            php.ini only
zend_extension_ts                     NULL                                            php.ini only
zlib.output_compression               "0"                                             PHP_INI_ALL    从 PHP 4.0.5 起可用。
zlib.output_compression_level         ""                                              PHP_INI_ALL    从 PHP 4.3.0 起可用。
zlib.output_handler                   ""                                              PHP_INI_ALL    从 PHP 4.3.0 起可用。
===================================== =============================================== ============== ================================================================
