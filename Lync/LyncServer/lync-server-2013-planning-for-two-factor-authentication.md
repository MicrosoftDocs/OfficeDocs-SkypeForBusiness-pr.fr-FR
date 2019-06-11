---
title: 'Lync Server 2013: planification de l’authentification à deux facteurs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for two-factor authentication
ms:assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308562(v=OCS.15)
ms:contentKeyID: 54973683
ms.date: 04/06/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 299d2328ee11ffb893974e48b86922123145ed72
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824210"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-two-factor-authentication-in-lync-server-2013"></a>Planification de l’authentification à deux facteurs dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2015-04-06_

La liste suivante répertorie les éléments à prendre en compte lors de la configuration d’un environnement Microsoft Lync Server 2013 pour prendre en charge l’authentification à deux facteurs.

<div>

## <a name="client-support"></a>Prise en charge des clients

Les mises à jour cumulatives de Lync 2013 pour Lync Server 2013: le client de bureau 2013 de juillet et tous les clients mobiles prennent actuellement en charge l’authentification à deux facteurs.

</div>

<div>

## <a name="topology-requirements"></a>Conditions requises pour la topologie

Les clients sont fortement invités à déployer l’authentification à deux facteurs à l’aide de la 2013 dédiée de Lync Server avec des mises à jour cumulatives pour Lync Server 2013:2013 Edge, Director et groupes d’utilisateurs. Pour activer l’authentification passive pour les utilisateurs de Lync, les autres méthodes d’authentification doivent être désactivées pour les autres rôles et services, notamment les suivantes:


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
<td><p>Serveur d’inscriptions avancé</p></td>
<td><p>Serveur frontal</p></td>
<td><p>Kerberos et NTLM</p></td>
</tr>
</tbody>
</table>


Si ces types d’authentifications ne sont pas désactivés au niveau du service, toutes les autres versions du client Lync ne seront pas en mesure de se connecter une fois que l’authentification à deux facteurs est activée dans le cadre de votre déploiement.

</div>

<div>

## <a name="lync-service-discovery"></a>Découverte de service Lync

Les enregistrements DNS utilisés par les clients internes et/ou externes pour détecter les services Lync doivent être configurés pour une résolution sur un serveur Lync qui n’est pas activé pour l’authentification à deux facteurs. Dans cette configuration, les utilisateurs de pools Lync qui ne sont pas activés pour l’authentification à deux facteurs ne seront pas obligés d’entrer un code confidentiel pour s’authentifier, alors que les utilisateurs de pools Lync qui sont activés pour l’authentification à deux facteurs seront obligés d’entrer leur code confidentiel Authenticate.

</div>

<div>

## <a name="exchange-authentication"></a>Authentification Exchange

Les clients qui ont déployé l’authentification à deux facteurs pour Microsoft Exchange peuvent constater que certaines fonctionnalités du client Lync ne sont pas disponibles. Cette fonctionnalité est actuellement à l’étude, car le client Lync ne prend pas en charge l’authentification à deux facteurs pour les fonctionnalités qui dépendent de l’intégration Exchange.

</div>

<div>

## <a name="lync-contacts"></a>Contacts Lync

Les utilisateurs de Lync qui sont configurés pour utiliser la fonctionnalité de magasin de contacts unifiée pourront constater que leurs contacts ne sont plus disponibles une fois que vous êtes connecté à l’aide de l’authentification à deux facteurs.

Pour activer l’authentification à deux facteurs, vous devez utiliser l’applet de passe **Invoke-CsUcsRollback** pour supprimer les contacts des utilisateurs existants du magasin de contacts unifié et les stocker dans Lync Server 2013.

</div>

<div>

## <a name="skill-search"></a>Recherche de compétences

Les clients qui ont configuré la fonction de recherche de compétences dans leur environnement Lync constateront que cette fonctionnalité ne fonctionne pas lorsque Lync est activé pour l’authentification à deux facteurs. Ce comportement est normal, car Microsoft SharePoint ne prend pas en charge l’authentification à deux facteurs pour le moment.

</div>

<div>

## <a name="lync-credentials"></a>Informations d’identification Lync

Il existe un certain nombre de considérations de déploiement impliquant des informations d’identification Lync enregistrées qui peuvent avoir un impact sur les utilisateurs qui sont configurés pour utiliser l’authentification à deux facteurs.

<div>

## <a name="deleting-saved-credentials"></a>Suppression des informations d’identification enregistrées

Les utilisateurs du client de bureau doivent utiliser l’option **Supprimer mes informations de connexion** dans le client Lync et supprimer leur dossier de profil SIP de\\%\\LocalAppData\\%\\Microsoft Office 15,0 Lync avant d’essayer de vous connecter pour la première fois utilisation de l’authentification à deux facteurs.

</div>

<div>

## <a name="disablentcredentials"></a>DisableNTCredentials

Lorsque la méthode d’authentification Kerberos ou NTLM est utilisée, les informations d’identification Windows de l’utilisateur sont utilisées automatiquement pour l’authentification. Dans le cas d’un déploiement standard de Lync Server 2013 sur lequel Kerberos et/ou NTLM est activé pour l’authentification, l’utilisateur ne doit pas entrer ses informations d’identification chaque fois qu’il se connecte.

Si les utilisateurs sont invités à entrer leurs informations d’identification avant leur code confidentiel, la clé de Registre **DisableNTCredentials** est peut être configurée involontairement sur les ordinateurs clients, éventuellement par le biais de la stratégie de groupe.

Pour empêcher l’invite supplémentaire pour les informations d’identification, créez l’entrée de Registre suivante sur la station de travail locale ou utilisez le modèle d’administration Lync pour appliquer à tous les utilisateurs pour un pool donné à l’aide d’une stratégie de groupe:

HKEY\_stratégies\_\\\\\\logicielles\\locales Microsoft Office 15,0\\\\

REG\_DWORD: DisableNTCredentials

Valeur : 0x0

</div>

<div>

## <a name="savepassword"></a>SavePassword

Lorsqu’un utilisateur se connecte à Lync pour la première fois, l’utilisateur est invité à enregistrer son mot de passe. Lorsqu’elle est sélectionnée, cette option permet le stockage du certificat client de l’utilisateur dans le magasin de certificats personnel et des informations d’identification Windows de l’utilisateur dans le Gestionnaire d’informations d’identification de l’ordinateur local.

Le paramètre de Registre **SavePassword** doit être désactivé lorsque Lync est configuré pour prendre en charge l’authentification à deux facteurs. Pour empêcher les utilisateurs d’enregistrer leur mot de passe, modifiez l’entrée de Registre suivante sur la station de travail locale ou utilisez le modèle d’administration Lync pour appliquer à tous les utilisateurs pour un pool donné à l’aide d’une stratégie de groupe:

HKEY\_logiciel\_\\utilisateur\\actuel Microsoft\\Office\\15,0\\Lync

REG\_DWORD: SavePassword

Valeur : 0x0

</div>

</div>

<div>

## <a name="ad-fs-20-token-replay"></a>Relecture des jetons d’AD FS 2.0

La fonctionnalité d’AD FS 2.0 de détection de relecture des jetons détecte et rejette les demandes de jeton multiples effectuées à l’aide d’un même jeton. Lorsqu’elle est activée, elle protège l’intégrité des demandes d’authentification dans le profil passif WS-Federation et le profil SAML WebSSO en vérifiant que le même jeton n’est pas utilisé plusieurs fois.

Cette fonctionnalité doit être activée dans les cas dans lesquels la sécurité constitue un aspect essentiel, par exemple, dans le cadre de l’utilisation des kiosques. Pour plus d’informations sur la détection de relecture de jeton, voir recommandations en matière de planification et de déploiement [http://go.microsoft.com/fwlink/p/?LinkId=309215](http://go.microsoft.com/fwlink/p/?linkid=309215)sécurisés d’AD FS 2,0 à l’adresse.

</div>

<div>

## <a name="external-user-access"></a>Accès des utilisateurs externes

La configuration d’un proxy AD FS ou d’un proxy inverse pour prendre en charge l’authentification à deux facteurs de Lync à partir de réseaux externes n’est pas décrite dans les rubriques suivantes.

</div>

</div>

<span> </span>

</div>

</div>

</div>

