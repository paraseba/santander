# Santander driver script

Script que usa watir-webdriver (selenium) para usar la página del Santander Argentina.

Cree un archivo en el mismo directorio que el script, llamado passwords-santander.rb

En ese archivo ponga:

```ruby
{:dni=>"mydni", :numeric_password=>"4 digit pwd",
 :password=>"your complex password",
 :transfer_card=>["51", "25", "11", "60". all your numbers in order ......]}
```

Encripte el archivo usando `gpg -c --cipher-algo BLOWFISH passwords-santander.rb` o
cualquier otro cipher. Esto pedirá un passphrase y generará un archivo
passwords-santander.rb.gpg. Borre el archivo orginal.

Corra el script para tener instrucciones.

## Disclaimer

El script es un 30 minutes hack, no tiene pretenciones de buena programación.

## Dependencias

- Ruby
- zenity
- gem 'watir-webdriver'
- gpg

## Contributing

Como sea, cualquier ayuda para agregar operaciones o mejorar el script será bienvenida.

## History

- Initial version
  - Login
  - Transferencias, con login y tarjeta de coordenadas
  - Las transferencias pueden ser sin destinatario o con un string que matchee
  alguna cuenta ya creada en la agenda le Santander
  - Download de xls de últimos movimientos y resúmenes de tarjetas
  - Download de todos resúmenes de cuenta disponibles
  - Consulta de saldo de cuentas
  - Inflexible, asume un montón de cosas, probablemente me funcione solo a mí.
