---
title: 'Lync Server 2013 : Processus de déploiement pour la mobilité'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for mobility
ms:assetid: 5a1cebda-c14b-4ff4-9c36-f7caa868160f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690023(v=OCS.15)
ms:contentKeyID: 48184220
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6f9f7994981a860aaa02d4674d6a3248c3593d6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762592"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-mobility-in-lync-server-2013"></a>Processus de déploiement pour la mobilité dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-19_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013. It is noted accordingly.

Cette section décrit la procédure de déploiement de la fonctionnalité de mobilité de Lync Server 2013.

### <a name="mobility-deployment-process"></a>Processus de déploiement de mobilité

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Phase</th>
<th>Étapes</th>
<th>Autorisations</th>
<th>Documentation de déploiement</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Créer des enregistrements DNS (Domain Name System)</p></td>
<td><ul>
<li><p>Créer un enregistrement DNS CNAMe interne ou A (hôte, si IPv6, AAAA) pour résoudre l’URL du service de découverte automatique interne.</p></li>
<li><p>Créer un enregistrement DNS canonique ou A (hôte, si IPv6, AAAA) pour résoudre l’URL du service de découverte automatique externe.</p></li>
</ul></td>
<td><p>DomainAdmins</p>
<p>DnsAdmins</p></td>
<td><p><a href="lync-server-2013-creating-dns-records-for-the-autodiscover-service.md">Création d’enregistrements DNS pour le service de découverte automatique dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Modifier les certificats</p></td>
<td><p>Ajoutez des entrées de nom de remplacement d’objet aux certificats suivants pour prendre en charge des connexions sécurisées pour les utilisateurs mobiles :</p>
<ul>
<li><p>Certificat de réalisateur</p></li>
<li><p>Certificat de pool frontal</p></li>
<li><p>Certificat de proxy inverse</p></li>
</ul></td>
<td><p>Administrateur local</p></td>
<td><p><a href="lync-server-2013-modifying-certificates-for-mobility.md">Modification des certificats pour la mobilité dans Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Configurer le proxy inverse</p></td>
<td><ul>
<li><p>Attribuez des certificats mis à jour avec des noms de substitution d’objet à l’écouteur SSL (Secure Sockets Layer).</p></li>
<li><p>Reconfigurez la règle de publication Web pour l’URL du service de découverte automatique externe.</p></li>
<li><p>Assurez-vous qu’une règle de publication sur le Web existe pour l’URL des services Web Lync Server 2013 externes de votre pool frontal.</p></li>
</ul>
<p>Ou</p>
<ul>
<li><p>Si vous choisissez d’utiliser HTTP pour la demande de découverte automatique initiale et de ne pas mettre à jour les listes de noms alternatifs d’objet sur les certificats, configurez une nouvelle règle de publication Web ou reconfigurez une règle de publication existante pour le port 80 HTTP.</p></li>
</ul></td>
<td><p>Administrateur local</p></td>
<td><p><a href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configuration du proxy inverse pour la mobilité dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Tester le déploiement de votre mobilité pour Lync 2010 mobile à l’aide du service de mobilité MCX</p></td>
<td><p>Exécutez <strong>test-CsMcxP2PIM</strong> pour tester l’envoi d’un message instantané d’une personne à l’autre.</p>
<p>Pour obtenir la liste complète des options, reportez-vous à la documentation cmdlet de Lync Server Management Shell pour <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM">test-CsMcxP2PIM</a> .</p></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-verifying-your-mobility-deployment.md">Vérification du déploiement de mobilité dans Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Tester le déploiement de votre mobilité pour les clients mobiles Lync 2013 à l’aide des composants Web UCWA</p></td>
<td><p>Utilisez l’applet de <strong>contrôle test-CsUcwaConference</strong> pour tester et vérifier que les utilisateurs de tests prédéfinis ou une paire d’utilisateurs réels peuvent utiliser UCWA pour créer une conférence et y participer.</p>
<p>Pour obtenir la liste complète des options, reportez-vous à la documentation cmdlet de Lync Server Management Shell pour <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference">test-CsUcwaConference</a> .</p></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-verifying-your-mobility-deployment.md">Vérification du déploiement de mobilité dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Configurer les notifications push</p></td>
<td><ul>
<li><p>Pour les serveurs Edge Lync Server 2013, ajoutez un fournisseur d’hébergement Lync Server Online et configurez la Fédération du fournisseur d’hébergement.</p></li>
<li><p>Pour les serveurs Edge Lync Server 2010, ajoutez un fournisseur d’hébergement Lync Server Online et configurez la Fédération du fournisseur d’hébergement.</p></li>
<li><p>Pour les serveurs Edge Office Communications Server 2007 R2, ajoutez un partenaire fédéré.</p></li>
<li><p>Si vous voulez prendre en charge les notifications de transmission via un réseau Wi-Fi, configurez une règle de pare-feu sortante pour le port TCP 5223.</p></li>
<li><p>Utilisez l’applet de cmdlet <strong>Set-CsPushNotificationConfiguration</strong> pour activer les notifications de transmission pour les services de notifications de transmission d’Apple (APNs) et Microsoft émission notification service (MPNS). Cette fonctionnalité est désactivée par défaut.</p></li>
<li><p>Utilisez l’applet de <strong>contrôle test-CsFederatedPartner</strong> pour tester la configuration de la Fédération et l’applet de <strong>contrôle CsMCXPushNotification de test</strong> pour tester les notifications de transmission.</p>
<div>

> [!NOTE]  
> Les notifications de transmission sont utilisées pour les clients mobiles Lync 2010 sur les appareils Apple et Windows Phone<BR>La notification de transmission est requise pour les clients mobiles Lync 2013 sur Windows Phone uniquement


</div></li>
</ul></td>
<td><p>RtcUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configuring-for-push-notifications.md">Configuration des notifications push dans Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Configurer une stratégie de mobilité</p></td>
<td><p>Utilisez l’applet de cmdlet <strong>Set-CsMobilityPolicy</strong> pour autoriser ou rejeter les éléments suivants :</p>
<ul>
<li><p>Appel via le bureau</p></li>
<li><p>Activer les appels audio et vidéo IP</p></li>
<li><p>Wi-Fi requis pour les appels audio et/ou vidéo IP</p></li>
</ul></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configuring-mobility-policy.md">Configuration de la stratégie de mobilité dans Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

