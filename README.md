# Spring Security II

## Tabla de contenido

- [Autenticación y autorización avanzada](#autenticacion-y-autorizacion-avanzada)
  - [Autenticación sin estado (Stateless Authentication)](#autenticacion-sin-estado)
    - [JSON Web Tokens (JWT)](#json-web-tokens)
      - [Estructura y firma de JWT (JWS, JWE)](#estructura-y-firma-de-un-jwt)
      - [Generación y validación de JWT con Spring Security](#generacion-y-validacion-de-jwt)
      - [Manejo de tokens de acceso y refrescamiento (refresh tokens)](#access-y-refresh-token)
      - [Estrategias de revocación de JWT](#estrategias-de-revocacion-de-tokens)
    - [Integración de JWT con Spring Security para APIs RESTful](#integracion-con-jwt-y-una-api-rest)
  - [OAuth 2.0 y OpenID Connect (OIDC)](#oauth-2.0-y-opendid)
    - [Conceptos básicos](#conceptos-basicos-de-oauth)
      - [Roles](#roles)
      - [Flujos de conseción](#flujos-de-consecion)
      - [Tokens](#tokens)
    - [Spring Security OAuth2 Client](#spring-security-client) 
    - [Integración con proveedores externos](#integracion-con-proveedores-externos)
      - [Integración con el proveedor de Google](#proveedor-google)
      - [Integración con el proveedor de GitHub](#proveedor-github)
    - [Roles de usuario y mapeo de claims de OIDC](#roles-de-usario-y-claims-oidc)
    - [Implementación de un servidor de autorización OAuth 2.0](#servidor-de-autorizacion)
      - [Uso de Spring Authorization Server](#spring-authorization-server)
  - [Autenticación Multifactor (MFA/2FA)](#autenticacion-multifactor)
    - [Conceptos y tipos de MFA](#tipos-de-mfa)
      - [OTP por tiempo](#otp-por-tiempo)
      - [OTP por contador](#otp-por-contador)
      - [Biometría](#biometria)
    - [MFA en una aplicación Spring Boot](#mfa-en-una-aplicacion-de-spring)
      - [Ejemplos prácticos con librerías o servicios de terceros](#ejemplos-practicos-de-mfa)
- [Integración con proveedores de identidad (IDP)](#proveedores-de-identidad)
    - [Integración con Keycloak](#integracion-con-keycloak)
      - [¿Qué es Keycloak y por qué usarlo?](#que-es-keycloak-por-que-usarlo)
      - [Integración de Spring Security como cliente](#spring-security-como-cliente-para-keycloak)
      - [Roles y grupos de Keycloak](#roles-y-grupos-en-keycloak)
        - [Mapeo a Spring Security](#mapeo-de-roles-a-spring-security)
      - [Single Sign-On (SSO) con Keycloak](#sso-con-keycloak)
    - [SAML 2.0 (Security Assertion Markup Language)](#saml-2.0)
      - [Introducción a SAML y sus casos de uso](#casos-de-uso-de-saml-2.0)
      - [Service Provider (SP) de SAML con Spring Security](#sp-de-sml-con-spring-security)
      - [Integración con identity providers (IdP) basados en SAML](#integracion-con-identity-providers)
- [Prácticas de seguridad adicionales](#practicas-de-seguridad-adicionales)
    - [Rate limiting y throttling](#rate-limiting-y-throttling)
    - [Spring Security Actuator Endpoints](#spring-security-actuator)
      - [Monitoreo y gestión de la seguridad de la aplicación](#monitoreo-y-gestion-de-la-seguridad-en-la-app)
    - [Auditoría y logging de seguridad](#auditoria-y-logging-de-seguridad)
      - [Registro de eventos de seguridad](#registro-de-eventos-de-seguridad)
      - [Integración con herramientas de SIEM](#herramientas-siem)
    - [Políticas de contraseñas y gestión de cuentas](#politicas-de-contraseñas-y-gestion-de-cuentas)
      - [Buenas prácticas para la gestión de contraseñas](#gestion-de-contraseñas)
      - [Recuperación de cuenta de manera segura](#recuperacion-de-contraseña-segura)
      - [Bloqueo de cuentas](#bloqueo-de-cuentas)


<a id="autenticacion-y-autorizacion-avanzada"></a>
## Autenticación y autorización avanzada

<a id="autenticacion-sin-estado"></a>
### Autenticación sin estado (Stateless Authentication)

<a id="json-web-tokens"></a>
#### JSON Web Tokens (JWT)

<a id="estructura-y-firma-de-un-jwt"></a>
##### Estructura y firma de JWT (JWS, JWE)

<a id="generacion-y-validacion-de-jwt"></a>
##### Generación y validación de JWT con Spring Security

<a id="access-y-refresh-token"></a>
##### Manejo de tokens de acceso y refrescamiento (refresh tokens)

<a id="estrategias-de-revocacion-de-tokens"></a>
##### Estrategias de revocación de JWT

<a id="integracion-con-jwt-y-una-api-rest"></a>
#### Integración de JWT con Spring Security para APIs RESTful

<a id="oauth-2.0-y-opendid"></a>
### OAuth 2.0 y OpenID Connect (OIDC)

<a id="conceptos-basicos-de-oauth"></a>
#### Conceptos básicos

<a id="roles"></a>
##### Roles

<a id="flujos-de-consecion"></a>
##### Flujos de conseción

<a id="tokens"></a>
##### Tokens

<a id="spring-security-client"></a>
#### Spring Security OAuth2 Client

<a id="integracion-con-proveedores-externos"></a>
#### Integración con proveedores externos

<a id="proveedor-google"></a>
##### Integración con el proveedor de Google

<a id="proveedor-github"></a>
##### Integración con el proveedor de GitHub

<a id="roles-de-usario-y-claims-oidc"></a>
#### Roles de usuario y mapeo de claims de OIDC](#roles-de-usario-y-claims-oidc)

<a id="servidor-de-autorizacion"></a>
#### Implementación de un servidor de autorización OAuth 2.0

<a id="spring-authorization-server"></a>
##### Uso de Spring Authorization Server

<a id="autenticacion-multifactor"></a>
### Autenticación Multifactor (MFA/2FA)

<a id="tipos-de-mfa"></a>
#### Conceptos y tipos de MFA

<a id="otp-por-tiempo"></a>
##### OTP por tiempo

<a id="otp-por-contador"></a>
##### OTP por contador

<a id="biometria"></a>
##### Biometría

<a id="mfa-en-una-aplicacion-de-spring"></a>
#### MFA en una aplicación Spring Boot

<a id="ejemplos-practicos-de-mfa"></a>
##### Ejemplos prácticos con librerías o servicios de terceros

<a id="proveedores-de-identidad"></a>
## Integración con proveedores de identidad (IDP)

<a id="integracion-con-keycloak"></a>
### Integración con Keycloak

<a id="que-es-keycloak-por-que-usarlo"></a>
#### ¿Qué es Keycloak y por qué usarlo?

<a id="spring-security-como-cliente-para-keycloak"></a>
#### Integración de Spring Security como cliente

<a id="roles-y-grupos-en-keycloak"></a>
#### Roles y grupos de Keycloak

<a id="mapeo-de-roles-a-spring-security"></a>
##### Mapeo a Spring Security

<a id="sso-con-keycloak"></a>
#### Single Sign-On (SSO) con Keycloak

<a id="saml-2.0"></a>
### SAML 2.0 (Security Assertion Markup Language)

<a id="casos-de-uso-de-saml-2.0"></a>
#### Introducción a SAML y sus casos de uso

<a id="sp-de-sml-con-spring-security"></a>
#### Service Provider (SP) de SAML con Spring Security

<a id="integracion-con-identity-providers"></a>
#### Integración con identity providers (IdP) basados en SAML

<a id="practicas-de-seguridad-adicionales"></a>
## Prácticas de seguridad adicionales

<a id="rate-limiting-y-throttling"></a>
### Rate limiting y throttling

<a id="spring-security-actuator"></a>
### Spring Security Actuator Endpoints

<a id="monitoreo-y-gestion-de-la-seguridad-en-la-app"></a>
#### Monitoreo y gestión de la seguridad de la aplicación

<a id="auditoria-y-logging-de-seguridad"></a>
### Auditoría y logging de seguridad

<a id="registro-de-eventos-de-seguridad"></a>
#### Registro de eventos de seguridad

<a id="herramientas-siem"></a>
#### Integración con herramientas de SIEM

<a id="politicas-de-contraseñas-y-gestion-de-cuentas"></a>
### Políticas de contraseñas y gestión de cuentas

<a id="gestion-de-contraseñas"></a>
#### Buenas prácticas para la gestión de contraseñas

<a id="recuperacion-de-contraseña-segura"></a>
#### Recuperación de cuenta de manera segura

<a id="bloqueo-de-cuentas"></a>
#### Bloqueo de cuentas


