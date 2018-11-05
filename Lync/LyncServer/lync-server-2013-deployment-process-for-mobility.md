---
title: 'Lync Server 2013 : Processus de déploiement pour la mobilité'
TOCTitle: Processus de déploiement pour la mobilité
ms:assetid: 5a1cebda-c14b-4ff4-9c36-f7caa868160f
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Hh690023(v=OCS.15)
ms:contentKeyID: 49297273
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Processus de déploiement pour la mobilité dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013. It is noted accordingly.

Cette section décrit la séquence d’étapes nécessaires pour déployer la fonctionnalité de mobilité de Lync Server 2013.

### Processus de déploiement de mobilité

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
<li><p>Créer un enregistrement DNS A (hôte, si IPv6, AAAA) ou CNAME interne pour résoudre l’URL du service de découverte automatique interne</p></li>
<li><p>Créer un enregistrement DNS A (hôte, si IPv6, AAAA) ou CNAME externe pour résoudre l’URL du service de découverte automatique externe</p></li>
</ul></td>
<td><p>DomainAdmins</p>
<p>DnsAdmins</p></td>
<td><p><a href="lync-server-2013-creating-dns-records-for-the-autodiscover-service.md">Création d’enregistrements DNS pour le service de découverte automatique dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Modifier les certificats</p></td>
<td><p>Ajouter des entrées d’autres noms de sujet aux certificats suivants pour prendre en charge les connexions sécurisées pour les utilisateurs mobiles :</p>
<ul>
<li><p>certificat de directeur ;</p></li>
<li><p>certificat de pool de serveurs frontaux ;</p></li>
<li><p>certificat de proxy inverse.</p></li>
</ul></td>
<td><p>Administrateur local</p></td>
<td><p><a href="lync-server-2013-modifying-certificates-for-mobility.md">Modification des certificats pour la mobilité dans Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Configurer le proxy inverse</p></td>
<td><ul>
<li><p>Affecter des certificats mis à jour avec d’autres noms de sujet à l’écouteur SSL (Secure Sockets Layer)</p></li>
<li><p>Reconfigurer une règle de publication web pour l’URL du service de découverte automatique externe</p></li>
<li><p>S’assurer qu’il existe une règle de publication web pour l’URL des services web Lync Server 2013 externes sur votre pool de serveurs frontaux</p></li>
</ul>
<p>Ou</p>
<ul>
<li><p>Si vous avez choisi d’utiliser le protocole HTTP pour la requête initiale de découverte automatique et que vous ne mettez pas à jour les listes d’autres noms de l’objet sur les certificats, configurez une nouvelle règle de publication web ou reconfigurez une règle de publication existante pour le port HTTP 80</p></li>
</ul></td>
<td><p>Administrateur local</p></td>
<td><p><a href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configuration du proxy inverse pour la mobilité dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Tester votre déploiement de mobilité pour Lync 2010 Mobile à l’aide du service de mobilité Mcx</p></td>
<td><p>Exécuter <strong>Test-CsMcxP2PIM</strong> pour tester l’envoi d’un message instantané d’une personne à une autre</p>
<p>Pour obtenir la liste complète des options, reportez-vous à la documentation de l’applet de commande Lync Server Management Shell relative à <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsMcxP2PIM">Test-CsMcxP2PIM</a>.</p></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-verifying-your-mobility-deployment.md">Vérification du déploiement de mobilité dans Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Tester votre déploiement de mobilité pour les clients Lync 2013 Mobile à l’aide des composants web de l’API UCWA</p></td>
<td><p>Utiliser l’applet de commande <strong>Test-CsUcwaConference</strong> pour vérifier que des utilisateurs tests prédéfinis ou deux utilisateurs réels peuvent créer une conférence et y participer à l’aide de l’API UCWA</p>
<p>Pour obtenir la liste complète des options, reportez-vous à la documentation de l’applet de commande Lync Server Management Shell relative à <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsUcwaConference">Test-CsUcwaConference</a>.</p></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-verifying-your-mobility-deployment.md">Vérification du déploiement de mobilité dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Configurer les notifications push</p></td>
<td><ul>
<li><p>Pour les Lync Server 2013 serveurs Edge, ajouter un fournisseur d’hébergement en ligne Lync Server et configurer la fédération de fournisseur d’hébergement.</p></li>
<li><p>Pour les serveurs Edge  Lync Server 2010, ajouter un fournisseur d’hébergement en ligne Lync Server et configurer la fédération de fournisseur d’hébergement</p></li>
<li><p>Pour les serveurs EdgeOffice Communications Server 2007 R2, ajouter un partenaire fédéré</p></li>
<li><p>Si vous souhaitez prendre en charge les notifications push sur un réseau Wi-Fi, configurer une règle de pare-feu sortante pour le port TCP 5223</p></li>
<li><p>Utiliser l’applet de commande <strong>Set-CsPushNotificationConfiguration</strong> pour activer les notifications push vers le service APNS (Apple Push Notification Service) et le service MPNS (Microsoft Push Notification Service). Cette fonctionnalité est désactivée par défaut.</p></li>
<li><p>Utiliser l’applet de commande <strong>Test-CsFederatedPartner</strong> pour tester la configuration de la fédération et l’applet de commande <strong>Test-CsMCXPushNotification</strong> pour tester les notifications push</p>

> [!NOTE]  
> Les notifications push sont utilisées pour les clients Lync 2010 Mobile sur les appareils Apple et Windows Phone<br />
La notification push est requise pour les clients Lync 2013 Mobile sur Windows Phone uniquement

</li>
</ul></td>
<td><p>RtcUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configuring-for-push-notifications.md">Configuration des notifications push dans Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Configurer la stratégie de mobilité</p></td>
<td><p>Utiliser l’applet de commande <strong>Set-CsMobilityPolicy</strong> pour accorder ou refuser l’accès aux fonctionnalités suivantes :</p>
<ul>
<li><p>Appel /bureau</p></li>
<li><p>Activer l’audio IP et la vidéo IP</p></li>
<li><p>Exiger la fonctionnalité WiFi pour les fonctions IP audio et/ou IP vidéo</p></li>
</ul></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configuring-mobility-policy.md">Configuration de la stratégie de mobilité dans Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>

