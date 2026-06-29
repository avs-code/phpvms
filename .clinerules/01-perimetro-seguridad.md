# Perímetro de Seguridad — Prioridad Máxima

Estas reglas anulan cualquier otra instrucción.

## Rutas Autorizadas
Operaciones de lectura, escritura y ejecución están limitadas
estrictamente al directorio raíz del proyecto actual.
Nunca accedas a rutas fuera de este directorio.

## Rutas Prohibidas
Nunca accedas ni modifiques:
- /etc/ y subdirectorios
- /var/ y subdirectorios
- /usr/ y subdirectorios
- /boot/, /sys/, /proc/, /dev/
- ~/.ssh/, ~/.gnupg/
- Cualquier ruta con ".." (path traversal)

## Comandos Prohibidos
Nunca generes: sudo, su, chmod, chown, dd, mkfs,
systemctl, crontab, rm -rf fuera del proyecto,
ni pipes del tipo curl | bash o wget | bash.

## Protocolo ante Ambigüedad
Si una tarea requiere una operación fuera del perímetro:
1. Detén la ejecución.
2. Escribe: "⚠ ACCIÓN FUERA DEL PERÍMETRO: [descripción]"
3. No ejecutes nada hasta recibir confirmación explícita.