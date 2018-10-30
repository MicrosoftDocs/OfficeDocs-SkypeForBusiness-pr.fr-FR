---
title: 'Lync Server 2013 : Solutions de résistance de sites de succursale'
TOCTitle: Solutions de résistance de sites de succursale
ms:assetid: 1700f99b-709c-4e47-88eb-c0a5490e26e2
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398234(v=OCS.15)
ms:contentKeyID: 49296373
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Solutions de résistance de sites de succursale dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Mettre en œuvre la résistance des sites de succursale pour votre organisation présente des avantages évidents. Par exemple, si vous avez perdu la connexion au site central, les utilisateurs des sites de succursale continueront à bénéficier du service Voix Entreprise et de la messagerie vocale (si vous configurez les paramètres de reroutage de la messagerie vocale ; pour plus d’informations, reportez-vous à [Configuration requise pour la résistance des sites de succursale pour Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md)). Cependant, pour les sites comportant moins de 25 utilisateurs une solution de résistance peut ne pas être assez rentable.

Si vous décidez de mettre en œuvre la résistance pour les sites de succursale, vous disposez de trois options. Le tableau ci-dessous peut vous aider à déterminer l’option appropriée.



<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Si vous…</th>
<th>Nous vous recommandons d’utiliser un…</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Hébergez entre 25 et 1 000 utilisateurs sur le site de succursale, et si un déploiement complet n’est pas rentable ou si vous ne disposez pas d’un support d’administration local</p></td>
<td><p>Survivable Branch Appliance</p>
<p>Le Survivable Branch Appliance est un serveur lame standard avec un logiciel de serveur de médiation et d’inscriptions Lync Server fonctionnant sur Windows Server 2008 R2. Le Survivable Branch Appliance contient également une passerelle de réseau téléphonique commuté (RTC). Des périphériques tiers qualifiés (développés par les partenaires de Microsoft dans le programme de qualification/certification Survivable Branch Appliance (SBA) assurent une connexion RTC continue en cas de panne du réseau étendu, mais ils ne fournissent pas de services de conférence et de présence résistants, car ces fonctionnalités dépendent des serveurs frontaux du site central.</p>
<p>Pour plus d’informations sur les serveurs Survivable Branch Appliance, reportez-vous à « Survivable Branch Appliance en détail », dans la suite de cette rubrique.</p>
<p><strong>Remarque :</strong> si vous décidez d’utiliser également une jonction SIP avec le Survivable Branch Appliance, contactez le fabricant du Survivable Branch Appliance pour savoir quel fournisseur de services convient à votre organisation.</p></td>
</tr>
<tr class="even">
<td><p>Hébergez entre 1 000 et 2 000 utilisateurs sur le site de succursale, ne disposez pas d’une connexion de réseau étendu résistante mais disposez d’administrateurs Lync Server qualifiés</p></td>
<td><p>serveur Survivable Branch Server ou deux serveurs Survivable Branch Appliance</p>
<p>Le serveur Survivable Branch Server est un serveur Windows répondant à la configuration matérielle spécifiée et sur lequel le logiciel de serveur d’inscriptions et de médiation Lync Server est installé. Il doit se connecter à une passerelle RTC ou à une jonction SIP à un fournisseur de services téléphoniques.</p>
<p>Pour plus d’informations sur serveurs Survivable Branch Server, reportez-vous à « serveur Survivable Branch Server en détail » dans la suite de cette rubrique.</p></td>
</tr>
<tr class="odd">
<td><p>Si vous avez besoin de fonctionnalités de présence et de conférence en plus de fonctionnalités vocales pour 5 000 utilisateurs au maximum et si vous disposez d’administrateurs Lync Server qualifiés</p></td>
<td><p>Procédez à un déploiement de site central avec un serveur Standard Edition au lieu d’un déploiement de site de succursale.</p>
<p>Un déploiement complet de Lync Server fournit une connexion RTC continue et des fonctionnalités de présence et de conférence résistantes en cas de panne du réseau étendu.</p>
<p>Pour plus d’informations sur la préparation de cette solution, reportez-vous à <a href="lync-server-2013-planning-for-your-organization.md">Planification de l’organisation pour Lync Server 2013</a>, <a href="lync-server-2013-determining-your-system-requirements.md">Détermination de la configuration système requise pour Lync Server 2013</a>, <a href="lync-server-2013-determining-your-infrastructure-requirements.md">Définition de la configuration requise pour l’infrastructure pour Lync Server 2013</a> et d’autres sections connexes de la documentation de planification.</p></td>
</tr>
</tbody>
</table>


## Topologies résistantes

La figure suivante montre les topologies recommandées pour la résistance des sites de succursale.

**Options de résistance pour sites de succursale**

![Options de résilience de filiale vocale](images/Gg398234.47eecd19-08ae-4d82-acbe-61f0de760306(OCS.15).jpg "Options de résilience de filiale vocale")

## Survivable Branch Appliance en détail

Le Survivable Branch Appliance Lync Server comprend les composants suivants :

  - serveur d’inscriptions pour l’authentification et l’inscription des utilisateurs et routage des appels ;

  - serveur de médiation pour la signalisation entre le serveur d’inscriptions et la passerelle RTC ;

  - passerelle RTC pour le routage des appels vers le RTC comme moyen de transport secondaire en cas de panne du réseau étendu ;

  - SQL Server Express pour le stockage local des données d’utilisateur.

Le Survivable Branch Appliance comprend également des jonctions RTC, des ports analogiques et une carte réseau Ethernet.

Si la connexion de réseau étendu du site de succursale vers un site central n’est plus disponible, les utilisateurs internes du site de succursale peuvent continuer à s’enregistrer avec le serveur d’inscriptions du Survivable Branch Appliance et à obtenir un service vocal ininterrompu à l’aide de la connexion vers le RTC du Survivable Branch Appliance. De même, les utilisateurs du site de succursale se connectant de leur domicile ou d’autres emplacements distants pourront s’enregistrer avec un serveur d’inscriptions du site central si la liaison de réseau étendu vers le site de succursale est indisponible. Ces utilisateurs disposeront de la fonctionnalité de communication unifiée complète, la seule exception étant que les appels entrants vers le site de succursale seront transmis à la messagerie vocale. Lorsque la connexion de réseau étendu redevient disponible, les utilisateurs du site de succursale disposent de nouveau des fonctionnalités complètes de communication. Ni le basculement vers le Survivable Branch Appliance, ni la restauration du service ne nécessitent la présence d’un administrateur.

Lync Server prend en charge jusqu’à deux Survivable Branch Appliance sur un site de succursale.

## Vue d’ensemble du déploiement du Survivable Branch Appliance

Le Survivable Branch Appliance est fabriqué par des fabricants d’ordinateurs OEM en partenariat avec Microsoft et déployé par des distributeurs à valeur ajoutée. Ce déploiement doit avoir lieu seulement une fois que Lync Server a été déployé sur le site central, qu’une connexion de réseau étendu vers le site de succursale est établie et que Voix Entreprise est activé pour les utilisateurs de ce site.

Pour plus d’informations sur les phases ci-dessous, reportez-vous à [Déploiement d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server avec Lync Server 2013](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md) dans la documentation de déploiement.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Phase</th>
<th>Étapes</th>
<th>Droits d’utilisateur</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Installer les services de domaine Active Directory pour le Survivable Branch Appliance</p></td>
<td><p><strong>Sur le site central :</strong></p>
<ol>
<li><p>Créez un compte d’utilisateur de domaine (ou un identifiant d’entreprise) pour le technicien qui installera et activera le Survivable Branch Appliance sur le site de succursale.</p></li>
<li><p>Créez un compte d’ordinateur (avec le nom de domaine complet applicable) pour le Survivable Branch Appliance dans les services de domaine Active Directory.</p></li>
<li><p>Dans le Générateur de topologie, créez et publiez le Survivable Branch Appliance.</p></li>
</ol></td>
<td><p>Le compte d’utilisateur du technicien doit être membre du groupe RTCUniversalSBATechnicians. Le Survivable Branch Appliance doit appartenir au groupe RTCSBAUniversalServices, qui est créé automatiquement lorsque vous utilisez le générateur de topologie.</p></td>
</tr>
<tr class="even">
<td><p>Installer et activer le Survivable Branch Appliance.</p></td>
<td><p><strong>Sur le site de succursale :</strong></p>
<ol>
<li><p>Connectez le Survivable Branch Appliance à un port Ethernet et un port RTC.</p></li>
<li><p>Démarrez Survivable Branch Appliance.</p></li>
<li><p>Joignez le Survivable Branch Appliance au domaine, à l’aide du compte d’utilisateur créé pour le Survivable Branch Appliance du site central. Définissez le nom de domaine complet et l’adresse IP de sorte qu’ils correspondent au nom de domaine complet créé pour le compte d’utilisateur.</p></li>
<li><p>Configurez le Survivable Branch Appliance à l’aide de son interface utilisateur.</p></li>
<li><p>Testez la connectivité RTC.</p></li>
</ol></td>
<td><p>Le compte d’utilisateur du technicien doit être membre du groupe RTCUniversalSBATechnicians.</p></td>
</tr>
</tbody>
</table>


## Serveur Survivable Branch Server en détail

Dans le Générateur de topologie créez le site de succursale, ajoutez le serveur Survivable Branch Server à ce site, puis exécutez l’Assistant Déploiement de Lync Server sur l’ordinateur sur lequel vous souhaitez installer le rôle.

## Voir aussi

#### Autres ressources

[Déploiement de Lync Server 2013](lync-server-2013-deploying-lync-server.md)

