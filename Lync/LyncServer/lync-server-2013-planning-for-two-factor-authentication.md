---
title: 'Lync Server 2013 : planification de l’authentification à deux facteurs'
description: 'Lync Server 2013 : planification de l’authentification à deux facteurs.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for two-factor authentication
ms:assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308562(v=OCS.15)
ms:contentKeyID: 54973683
ms.date: 04/06/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a3a2cd5508f6ce9a8a389b0059a09747b9f9a09
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564000"
---
# <a name="planning-for-two-factor-authentication-in-lync-server-2013"></a>Planification de l’authentification à deux facteurs dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2015-04-06_

Voici une liste de considérations relatives au déploiement lors de la configuration d’un environnement Microsoft Lync Server 2013 afin de prendre en charge l’authentification à deux facteurs.

<div>

## <a name="client-support"></a>Prise en charge des clients

Les mises à jour cumulatives de Lync 2013 pour Lync Server 2013 : client de bureau de juillet 2013 et tous les clients mobiles prennent actuellement en charge l’authentification à deux facteurs.

</div>

<div>

## <a name="topology-requirements"></a>Conditions requises pour la topologie

Les clients sont vivement encouragés à déployer l’authentification à deux facteurs à l’aide de Lync Server 2013 dédié avec des mises à jour cumulatives pour Lync Server 2013 : juillet 2013 Edge, directeur et pools d’utilisateurs. Pour activer l’authentification passive pour les utilisateurs de Lync, les autres méthodes d’authentification doivent être désactivées pour les autres rôles et services, notamment les suivantes :


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
<th>Server Role</th>
<th>Type d’authentification à désactiver</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Service Web</p></td>
<td><p>WebServer</p></td>
<td><p>Directeur</p></td>
<td><p>Kerberos, NTLM et certificat</p></td>
</tr>
<tr class="even">
<td><p>Service Web</p></td>
<td><p>WebServer</p></td>
<td><p>Serveur frontal</p></td>
<td><p>Kerberos, NTLM et certificat</p></td>
</tr>
<tr class="odd">
<td><p>Établir</p></td>
<td><p>EdgeServer</p></td>
<td><p>Edge</p></td>
<td><p>Kerberos et NTLM</p></td>
</tr>
<tr class="even">
<td><p>Établir</p></td>
<td><p>Inscriptions</p></td>
<td><p>Serveur frontal</p></td>
<td><p>Kerberos et NTLM</p></td>
</tr>
</tbody>
</table>


À moins que ces types d’authentification soient désactivés au niveau du service, toutes les autres versions du client Lync ne pourront pas se connecter une fois que l’authentification à deux facteurs est activée dans dans votre déploiement.

</div>

<div>

## <a name="lync-service-discovery"></a>Découverte de service Lync

Les enregistrements DNS utilisés par les clients internes et/ou externes pour découvrir Lync services doivent être configurés pour être résolus en Lync Server qui n’est pas activé pour l’authentification à deux facteurs. Avec cette configuration, les utilisateurs des pools Lync qui ne sont pas activés pour l’authentification à deux facteurs ne seront pas tenus d’entrer un code confidentiel à authentifier, tandis que les utilisateurs des pools Lync qui sont activés pour l’authentification à deux facteurs doivent entrer leur code confidentiel pour s’authentifier.

</div>

<div>

## <a name="exchange-authentication"></a>Authentification Exchange

Les clients qui ont déployé l’authentification à deux facteurs pour Microsoft Exchange peuvent constater que certaines fonctionnalités du client Lync ne sont pas disponibles. Cette fonctionnalité est actuellement conçue par défaut, car le client Lync ne prend pas en charge l’authentification à deux facteurs pour les fonctionnalités qui dépendent de l’intégration d’Exchange.

</div>

<div>

## <a name="lync-contacts"></a>Contacts Lync

Les utilisateurs de Lync configurés pour tirer parti de la fonctionnalité de magasin de contacts unifié constateront que leurs contacts ne sont plus disponibles après la connexion à l’aide de l’authentification à deux facteurs.

Vous devez utiliser l’applet de commande **Invoke-CsUcsRollback** pour supprimer les contacts utilisateur existants du magasin de contacts unifié et les stocker dans Lync Server 2013 avant d’activer l’authentification à deux facteurs.

</div>

<div>

## <a name="skill-search"></a>Recherche de compétences

Les clients qui ont configuré la fonctionnalité de recherche de compétences dans leur environnement Lync constateront que cette fonctionnalité ne fonctionne pas lorsque Lync est activé pour l’authentification à deux facteurs. C’est par conception, car Microsoft SharePoint ne prend actuellement pas en charge l’authentification à deux facteurs.

</div>

<div>

## <a name="lync-credentials"></a>Informations d’identification Lync

Il existe un certain nombre de considérations relatives au déploiement impliquant des informations d’identification Lync enregistrées susceptibles d’avoir un impact sur les utilisateurs configurés pour utiliser l’authentification à deux facteurs.

<div>

## <a name="deleting-saved-credentials"></a>Suppression des informations d’identification enregistrées

Les utilisateurs des clients de bureau doivent utiliser l’option de **Suppression de mes informations de connexion** dans le client Lync et supprimer leur dossier de profil SIP de% LocalAppData% \\ Microsoft \\ Office \\ 15,0 \\ Lync avant de tenter de signer pour la première fois à l’aide de l’authentification à deux facteurs.

</div>

<div>

## <a name="disablentcredentials"></a>DisableNTCredentials

Avec la méthode d’authentification Kerberos ou NTLM, les informations d’identification Windows de l’utilisateur sont utilisées automatiquement pour l’authentification. Dans un déploiement standard de Lync Server 2013 où Kerberos et/ou NTLM sont activés pour l’authentification, les utilisateurs ne doivent pas nécessairement entrer leurs informations d’identification chaque fois qu’ils se connectent.

Si les utilisateurs sont involontairement invités à fournir des informations d’identification avant qu’ils ne soient invités à entrer leur code confidentiel, la clé de Registre **DisableNTCredentials** peut être involontairement configurée sur des ordinateurs clients, éventuellement par le biais de la stratégie de groupe.

Pour empêcher l’invite supplémentaire pour les informations d’identification, créez l’entrée de Registre suivante sur la station de travail locale ou utilisez le modèle d’administration Lync pour appliquer à tous les utilisateurs d’un pool donné à l’aide de la stratégie de groupe :

HKEY \_ \_ stratégies logicielles de l’ordinateur local \\ \\ \\ Microsoft \\ Office \\ 15,0 \\ Lync

REG \_ DWORD : DisableNTCredentials

Valeur : 0x0

</div>

<div>

## <a name="savepassword"></a>SavePassword

Lorsqu’un utilisateur se connecte à Lync pour la première fois, il est invité à enregistrer son mot de passe. Si cette option est sélectionnée, le certificat client de l’utilisateur est stocké dans le magasin de certificats personnel et les informations d’identification Windows de l’utilisateur sont stockées dans le gestionnaire d’informations d’identification de l’ordinateur local.

Le paramètre de Registre **SavePassword** doit être désactivé lorsque Lync est configuré pour prendre en charge l’authentification à deux facteurs. Pour empêcher les utilisateurs d’enregistrer leurs mots de passe, modifiez l’entrée de Registre suivante sur la station de travail locale ou utilisez le modèle d’administration Lync pour appliquer à tous les utilisateurs d’un pool donné à l’aide de la stratégie de groupe :

HKEY \_ Current \_ User \\ Software \\ Microsoft \\ Office \\ 15,0 \\ Lync

REG \_ DWORD : SavePassword

Valeur : 0x0

</div>

</div>

<div>

## <a name="ad-fs-20-token-replay"></a>Relecture des jetons AD FS 2,0

AD FS 2,0 fournit une fonctionnalité appelée détection de relecture de jeton, grâce à laquelle plusieurs demandes de jeton utilisant le même jeton peuvent être détectées, puis rejetées. Lorsque cette fonctionnalité est activée, la détection de relecture de jeton protège l’intégrité des demandes d’authentification dans WS-Federation le profil WebSSO passif et le profil SAML en s’assurant que le même jeton n’est jamais utilisé plusieurs fois.

Cette fonctionnalité doit être activée dans les situations où la sécurité est une préoccupation majeure, par exemple lors de l’utilisation de kiosques. Pour plus d’informations sur la détection de relecture de jetons, voir Best Practices for Secure Planning and Deployment of AD FS 2,0 à l’adresse [https://go.microsoft.com/fwlink/p/?LinkId=309215](https://go.microsoft.com/fwlink/p/?linkid=309215) .

</div>

<div>

## <a name="external-user-access"></a>Accès des utilisateurs externes

La configuration d’un proxy AD FS ou d’un proxy inverse pour prendre en charge l’authentification à deux facteurs de Lync à partir de réseaux externes n’est pas abordée dans ces rubriques.

</div>

</div>

<span> </span>

</div>

</div>

</div>

