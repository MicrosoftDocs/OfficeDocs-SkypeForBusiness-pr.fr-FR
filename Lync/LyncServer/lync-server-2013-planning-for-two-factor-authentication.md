---
title: Planification de l’authentification à deux facteurs
TOCTitle: Planification de l’authentification à deux facteurs
ms:assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Dn308562(v=OCS.15)
ms:contentKeyID: 56269567
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planification de l’authentification à deux facteurs

 

_**Dernière rubrique modifiée :** 2016-12-08_

La liste suivante répertorie les considérations relatives au déploiement dans le cadre de la configuration d’un environnement Microsoft Lync Server 2013 pour prendre en charge l’authentification à deux facteurs.

## Prise en charge des clients

Le client de bureau Lync 2013 avec les mises à jour cumulatives pour Lync Server 2013 de juillet 2013 est le seul client Lync prenant actuellement en charge l’authentification à deux facteurs.

## Conditions requises pour la topologie

Les clients sont fortement encouragés à déployer l’authentification à deux facteurs à l’aide de serveurs Edge, directeurs et pools d’utilisateur Lync Server 2013 avec les mises à jour cumulatives pour Lync Server 2013 de juillet 2013 dédiés. Pour activer l’authentification passive pour les utilisateurs de Lync, les autres méthodes d’authentification doivent être désactivées pour les autres rôles et services, notamment les suivantes :


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Type de configuration</th>
<th>Type de service</th>
<th>Rôle serveur</th>
<th>Type d’authentification à désactiver</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Service web</p></td>
<td><p>WebServer</p></td>
<td><p>Directeur</p></td>
<td><p>Kerberos, NTLM et par certificat</p></td>
</tr>
<tr class="even">
<td><p>Service web</p></td>
<td><p>WebServer</p></td>
<td><p>Serveur frontal</p></td>
<td><p>Kerberos, NTLM et par certificat</p></td>
</tr>
<tr class="odd">
<td><p>Proxy</p></td>
<td><p>EdgeServer</p></td>
<td><p>Edge</p></td>
<td><p>Kerberos et NTLM</p></td>
</tr>
<tr class="even">
<td><p>Proxy</p></td>
<td><p>Registrar</p></td>
<td><p>Serveur frontal</p></td>
<td><p>Kerberos et NTLM</p></td>
</tr>
</tbody>
</table>


Sauf si ces types d’authentifications sont désactivés au niveau du service, toutes les autres versions du client Lync ne pourront pas se connecter correctement une fois l’authentification à deux facteurs activée dans votre déploiement.

## Découverte des services Lync

Les enregistrements DNS utilisés par des clients internes et/ou externes pour découvrir les services Lync doivent être configurés pour être résolus vers un serveur Lync qui n’est pas activé pour l’authentification à deux facteurs. Avec cette configuration, les utilisateurs des pools Lync qui ne sont pas activés pour l’authentification à deux facteurs ne devront pas entrer de code confidentiel pour s’authentifier, contrairement aux utilisateurs des pools Lync activés pour l’authentification à deux facteurs.

## Authentification Exchange

Il est possible que les clients ayant déployé l’authentification à deux facteurs pour Microsoft Exchange ne puissent pas accéder à certaines fonctionnalités du client Lync. Ce comportement est normal, car le client Lync ne prend pas en charge l’authentification à deux facteurs pour les fonctionnalités qui dépendent de l’intégration Exchange, pour le moment.

## Contacts Lync

Les utilisateurs de Lync configurés pour utiliser la fonctionnalité Magasin de contact unifié ne pourront plus accéder à leurs contacts une fois connectés à l’aide de l’authentification à deux facteurs.

Vous devez utiliser l’applet de commande **Invoke-CsUcsRollback** pour supprimer les contacts existants du magasin de contact unifié et les stocker dans Lync Server 2013 avant d’activer l’authentification à deux facteurs.

## Recherche de compétences

Les clients qui ont configuré la fonctionnalité Recherche de compétences dans leur environnement Lync ne pourront pas y accéder lorsque Lync est activé pour l’authentification à deux facteurs. Ce comportement est normal, car Microsoft SharePoint ne prend pas en charge l’authentification à deux facteurs pour le moment.

## Informations d’identification de Lync

Diverses considérations relatives au déploiement et impliquant les informations d’identification Lync enregistrées peuvent affecter les utilisateurs configurés pour utiliser l’authentification à deux facteurs.

## Suppression des informations d’identification enregistrées

Les utilisateurs doivent sélectionner l’option **Supprimer mes informations de connexion** dans le client Lync et supprimer le dossier de profil SIP de %localappdata%\\Microsoft\\Office\\15.0\\Lync avant de se connecter pour la première fois via l’authentification à deux facteurs.

## DisableNTCredentials

Lorsque la méthode d’authentification Kerberos ou NTLM est utilisée, les informations d’identification Windows de l’utilisateur sont utilisées automatiquement pour l’authentification. Dans un déploiement Lync Server 2013 classique dans lequel Kerberos et/ou NTLM sont activés pour l’authentification, les utilisateurs ne doivent pas entrer leurs informations d’identification à chaque connexion.

Si les utilisateurs sont invités à entrer leurs informations d’identification avant leur code confidentiel, la clé de Registre **DisableNTCredentials** est peut être involontairement configurée sur les ordinateurs clients, éventuellement via la stratégie de groupe.

Pour empêcher l’affichage d’une nouvelle invite, créez l’entrée de Registre suivante sur la station de travail locale ou utilisez le modèle d’administration de Lync pour appliquer cette configuration à tous les utilisateurs d’un pool donné à l’aide de la stratégie de groupe :

HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Office\\15.0\\Lync

REG\_DWORD: DisableNTCredentials

Valeur : 0x0

## SavePassword

Lorsqu’un utilisateur se connecte à Lync la première fois, il est invité à enregistrer son mot de passe. Lorsqu’elle est sélectionnée, cette option permet le stockage du certificat client de l’utilisateur dans le magasin de certificats personnel et des informations d’identification Windows de l’utilisateur dans le Gestionnaire d’informations d’identification de l’ordinateur local.

Le paramètre de Registre **SavePassword** doit être désactivé lorsque Lync est configuré pour prendre en charge l’authentification à deux facteurs. Pour empêcher les utilisateurs d’enregistrer leur mot de passe, modifiez la clé de Registre suivante sur la station de travail locale ou utilisez le modèle d’administration de Lync pour appliquer cette configuration à tous les utilisateurs d’un pool donné à l’aide de la stratégie de groupe :

HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync

REG\_DWORD: SavePassword

Valeur : 0x0

## Relecture des jetons d’AD FS 2.0

La fonctionnalité d’AD FS 2.0 de détection de relecture des jetons détecte et rejette les demandes de jeton multiples effectuées à l’aide d’un même jeton. Lorsquֹ’elle est activée, elle protège l’intégrité des demandes d’authentification dans le profil passif WS-Federation et le profil SAML WebSSO en vérifiant que le même jeton n’est pas utilisé plusieurs fois.

Cette fonctionnalité doit être activée dans les cas dans lesquels la sécurité constitue un aspect essentiel, par exemple dans le cadre de l’utilisation des kiosques. Pour plus d’informations sur la détection de relecture des jetons, voir les meilleures pratiques pour la planification et le déploiement sécurisés d’AD FS 2.0 dans la page [http://go.microsoft.com/fwlink/p/?LinkId=309215](http://go.microsoft.com/fwlink/p/?linkid=309215).

## Accès des utilisateurs externes

La configuration d’un proxy ADFS ou d’un proxy inverse pour la prise en charge de l’authentification à deux facteurs de Lync à partir de réseaux externes n’est pas abordée dans ces rubriques.

