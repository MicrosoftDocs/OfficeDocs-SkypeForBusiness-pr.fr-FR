---
title: 'Lync Server 2013 : processus de déploiement pour la mobilité'
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
ms.openlocfilehash: f7d0e78cd4a8705178b3704a716846755d5c46f3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514481"
---
# <a name="deployment-process-for-mobility-in-lync-server-2013"></a>Processus de déploiement pour la mobilité dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-19_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013. It is noted accordingly.

Cette section décrit la séquence d’étapes nécessaires au déploiement de la fonctionnalité de mobilité Lync Server 2013.

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
<td><p>Créer des enregistrements DNS (Domain Name System).</p></td>
<td><ul>
<li><p>Créez un enregistrement DNS CNAMe ou A (hôte, si IPv6, AAAA) interne pour résoudre l’URL du service de découverte automatique interne.</p></li>
<li><p>Créez un enregistrement DNS CNAMe ou A (hôte, si IPv6, AAAA) externe pour résoudre l’URL du service de découverte automatique externe.</p></li>
</ul></td>
<td><p>Admins du domaine</p>
<p>DnsAdmins</p></td>
<td><p><a href="lync-server-2013-creating-dns-records-for-the-autodiscover-service.md">Création d’enregistrements DNS pour le service de découverte automatique dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Modifier les certificats</p></td>
<td><p>Ajouter des entrées d’autres noms de sujet aux certificats suivants pour prendre en charge les connexions sécurisées pour les utilisateurs mobiles :</p>
<ul>
<li><p>Certificat directeur</p></li>
<li><p>Certificat de pool frontal</p></li>
<li><p>certificat de proxy inverse.</p></li>
</ul></td>
<td><p>Administrateur local</p></td>
<td><p><a href="lync-server-2013-modifying-certificates-for-mobility.md">Modification des certificats pour la mobilité dans Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Configurer le proxy inverse</p></td>
<td><ul>
<li><p>Affecter des certificats mis à jour avec d’autres noms de sujet à l’écouteur SSL (Secure Sockets Layer)</p></li>
<li><p>Reconfigurez la règle de publication Web pour l’URL du service de découverte automatique externe.</p></li>
<li><p>Assurez-vous qu’il existe une règle de publication Web pour l’URL de services Web Lync Server 2013 externe sur votre pool frontal.</p></li>
</ul>
<p>Ou</p>
<ul>
<li><p>Si vous choisissez d’utiliser le protocole HTTP pour la demande de découverte automatique initiale et de ne pas mettre à jour les listes des autres noms de sujet sur les certificats, configurez une nouvelle règle de publication Web ou reconfigurez une règle de publication existante pour le port 80 HTTP.</p></li>
</ul></td>
<td><p>Administrateur local</p></td>
<td><p><a href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configuration du proxy inverse pour la mobilité dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Tester votre déploiement de mobilité pour Lync 2010 mobile à l’aide du service de mobilité MCX</p></td>
<td><p>Exécuter <strong>Test-CsMcxP2PIM</strong> pour tester l’envoi d’un message instantané d’une personne à une autre</p>
<p>Consultez la documentation de l’applet de commande Lync Server Management Shell pour <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM">test-CsMcxP2PIM</a> pour obtenir la liste complète des options.</p></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-verifying-your-mobility-deployment.md">Vérification de votre déploiement de mobilité dans Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Tester votre déploiement de mobilité pour les clients mobiles Lync 2013 utilisant les composants Web UCWA</p></td>
<td><p>La cmdlet <strong>test-CsUcwaConference</strong> permet de tester et de vérifier que les utilisateurs de test prédéfinis ou une paire d’utilisateurs réels peuvent utiliser UCWA pour créer et participer à une conférence.</p>
<p>Consultez la documentation de l’applet de commande Lync Server Management Shell pour <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference">test-CsUcwaConference</a> pour obtenir la liste complète des options.</p></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-verifying-your-mobility-deployment.md">Vérification de votre déploiement de mobilité dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Configurer les notifications de type push</p></td>
<td><ul>
<li><p>Pour les serveurs Edge Lync Server 2013, ajoutez un fournisseur d’hébergement Lync Server Online et configurez la Fédération des fournisseurs d’hébergement.</p></li>
<li><p>Pour les serveurs Edge Lync Server 2010, ajoutez un fournisseur d’hébergement Lync Server Online et configurez la Fédération des fournisseurs d’hébergement.</p></li>
<li><p>Pour les serveurs Edge Office Communications Server 2007 R2, ajoutez un partenaire fédéré.</p></li>
<li><p>Si vous souhaitez prendre en charge les notifications de type push sur un réseau Wi-Fi, configurer une règle de pare-feu sortante pour le port TCP 5223</p></li>
<li><p>Utiliser l’applet de commande <strong>Set-CsPushNotificationConfiguration</strong> pour activer les notifications de type push vers le service APNS (Apple Push Notification Service) et le service MPNS (Microsoft Push Notification Service). Cette fonctionnalité est désactivée par défaut.</p></li>
<li><p>Utiliser l’applet de commande <strong>Test-CsFederatedPartner</strong> pour tester la configuration de la fédération et l’applet de commande <strong>Test-CsMCXPushNotification</strong> pour tester les notifications de type push</p>
<div>

> [!NOTE]  
> Les notifications de type transmission sont utilisées pour les clients mobiles Lync 2010 sur les appareils Apple et Windows Phone<BR>La notification de type « transmission » est requise pour les clients mobiles Lync 2013 sur Windows Phone uniquement


</div></li>
</ul></td>
<td><p>RtcUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configuring-for-push-notifications.md">Configuration des notifications de type transmission dans Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Configurer la stratégie de mobilité</p></td>
<td><p>Utilisez l’applet de commande <strong>Set-CsMobilityPolicy</strong> pour activer ou désactiver :</p>
<ul>
<li><p>Appel via le Bureau</p></li>
<li><p>Activer l’audio IP et la vidéo IP</p></li>
<li><p>Exiger WiFi pour l’audio IP et/ou la vidéo IP</p></li>
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

