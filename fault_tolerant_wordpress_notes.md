## WordPress Notes - aCloud Guru

####

CloudFront ID
E1F3M96DBR976M

wp-config.php

<?php
/**
 * The base configuration for WordPress
 *
 * The wp-config.php creation script uses this file during the
 * installation. You don't have to use the web site, you can
 * copy this file to "wp-config.php" and fill in the values.
 *
 * This file contains the following configurations:
 *
 * * MySQL settings
 * * Secret keys
 * * Database table prefix
 * * ABSPATH
 *
 * @link https://codex.wordpress.org/Editing_wp-config.php
 *
 * @package WordPress
 */

// ** MySQL settings - You can get this info from your web host ** //
/** The name of the database for WordPress */
define('DB_NAME', 'acloudguru');

/** MySQL database username */
define('DB_USER', 'acloudguru');

/** MySQL database password */
define('DB_PASSWORD', 'acloudguru');

/** MySQL hostname */
define('DB_HOST', 'alcoudguru.cefilmmysjjm.us-east-1.rds.amazonaws.com:3306');

/** Database Charset to use in creating database tables. */
define('DB_CHARSET', 'utf8mb4');

/** The Database Collate type. Don't change this if in doubt. */
define('DB_COLLATE', '');

/**#@+
 * Authentication Unique Keys and Salts.
 *
 * Change these to different unique phrases!
 * You can generate these using the {@link https://api.wordpress.org/secret-key/1.1/salt/ WordPress.org secret-key service}
 * You can change these at any point in time to invalidate all existing cookies. This will force all users to have to log in again.
 *
 * @since 2.6.0
 */
define('AUTH_KEY',         'Pb!z=Is!=u}^h?Q lJVz#aI6!f3/TuRk?#laal<,43<t}UND2AF/?[b=5Wv@UN[9');
define('SECURE_AUTH_KEY',  ';_+MD9 !|*|ajpKMh+3ZNXW*7H2phn&6%MoXloUkVtdeH%ov@oe[ErDl6/X m7X?');
define('LOGGED_IN_KEY',    '(vtLP/YM-qawn/9A;,5u&[#*u*eVwTcpF_gfV0b9KgK^>Weo=x+nR7J1,+q%[mya');
define('NONCE_KEY',        'R*-OE9 $##)(%&d>mNISTs29([|k;N]>GZ|I<4?=gX#eP~mZ+-xL+5nQrMkYn?m9');
define('AUTH_SALT',        'Wk{IG4tx8XOo)L!EHASf`bYB#5lB_fA)PLEVf#|;lz9(_L$kj,lJKYl(j%QgUg9A');
define('SECURE_AUTH_SALT', 'mf[#@+_+#,N%Qj-N{6e[@6U/`D;]<+mg_KC+J`xYRZR1{ZGgYcffL#85nM_;]81=');
define('LOGGED_IN_SALT',   'aEWloIb@q_e8B{+;cHH#?xAZN@_0.;Nmij{qP)1RjPqzRz+oX.:9(EwL@8&*x6/Y');
define('NONCE_SALT',       '#KkOBiO1a478vN>*pc2#H1j|),.*^Cx!Xu6u.&K>C,xc3S;tyCHq-3ky>!QO<6;}');

/**#@-*/

/**
 * WordPress Database Table prefix.
 *
 * You can have multiple installations in one database if you give each
 * a unique prefix. Only numbers, letters, and underscores please!
 */
$table_prefix  = 'wp_';

/**
 * For developers: WordPress debugging mode.
 *
 * Change this to true to enable the display of notices during development.
 * It is strongly recommended that plugin and theme developers use WP_DEBUG
 * in their development environments.
 *
 * For information on other constants that can be used for debugging,
 * visit the Codex.
 *
 * @link https://codex.wordpress.org/Debugging_in_WordPress
 */
define('WP_DEBUG', false);

/* That's all, stop editing! Happy blogging. */

/** Absolute path to the WordPress directory. */
if ( !defined('ABSPATH') )
	define('ABSPATH', dirname(__FILE__) . '/');

/** Sets up WordPress vars and included files. */
require_once(ABSPATH . 'wp-settings.php');
