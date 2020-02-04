---
title: 'Lync Server 2013 : Liste de vérification du déploiement pour l’accès des utilisateurs externes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for external user access
ms:assetid: 3f55f502-88a0-4315-8783-45a32a0b78ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425910(v=OCS.15)
ms:contentKeyID: 48183947
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ad2ad90ab43402babdd10478e1d86cac2a38ddf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762722"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-external-user-access-in-lync-server-2013"></a>Liste de vérification du déploiement pour l’accès des utilisateurs externes dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-02-04_

Avant de déployer votre réseau de périmètre et de mettre en œuvre la prise en charge pour les utilisateurs externes, vous devez déjà avoir déployé vos serveurs internes Microsoft Lync Server 2013, y compris un pool frontal ou un serveur Standard Edition Server. Si vous envisagez de déployer les directeurs facultatifs dans votre réseau interne, vous devez également les déployer avant de déployer des serveurs Edge. Pour plus d’informations sur le processus de déploiement des directeurs, voir [scénarios pour le directeur dans Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) dans la documentation de planification.

Microsoft Lync Server 2013 inclut des outils permettant de faciliter la planification et le déploiement de serveurs intérieurs et de serveurs Edge. Une fois la topologie terminée, publiez la définition de topologie résultante dans votre environnement de production. Pour cela, vous devez être membre du groupe administrateurs de **domaine** et du groupe **RTCUniversalServerAdmins** .

  - **Outil de planification**   Office Communications Server 2007 R2 incluait un outil de planification et un outil de planification d’arête que vous pouvez utiliser pour vous aider à concevoir la topologie. Dans Lync Server 2010, ces deux outils étaient réunis en un seul outil de planification doté de fonctionnalités et de fonctionnalités supplémentaires, telles que la collecte du nombre d’utilisateurs planifiés, des exigences vocales, des types d’accès des utilisateurs externes et des options de Fédération. De plus, vous pouvez planifier les paramètres réseau de votre infrastructure, tels que les adresses IP, les types d’équilibrage de charge et les autres aspects du réseau de périmètre.

  - **Générateur de topologie**   Lync Server 2013 le générateur de topologie vous aide à définir votre topologie et vos composants. Le générateur de topologie est essentiel pour déployer des serveurs exécutant Lync Server 2013. Le générateur de topologie publie les résultats dans un magasin central de gestion utilisé pour configurer tous les serveurs exécutant Lync Server 2013 au sein de votre organisation. Vous ne pouvez pas installer Lync Server 2013 sur les serveurs sans utiliser le générateur de topologie.

Si vous avez conçu votre topologie latérale lors du processus de planification, y compris l’exécution du générateur de topologie pour définir votre topologie de périphérie, vous pouvez utiliser ces résultats pour démarrer le déploiement de votre serveur Edge. Si vous n’avez pas fini de générer votre topologie de périphérie ou si vous souhaitez modifier les informations que vous avez spécifiées, vous devez terminer d’exécuter le générateur de topologie avant d’effectuer d’autres étapes de déploiement. Pour plus d’informations sur la création de votre topologie, voir [scénarios d’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).

Pour plus d’informations sur l’outil de planification et le générateur de topologie, voir [commencer le processus de planification de Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) dans la documentation de planification.

Le tableau suivant fournit une vue d’ensemble du processus de déploiement de serveur Edge. Pour passer en revue les décisions de planification devant être prises avant de déployer l’accès des utilisateurs externes, voir [scénarios d’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).

<div>


> [!WARNING]  
> Les informations figurant dans le tableau suivant portent sur un nouveau déploiement. Si vous avez déployé des serveurs Edge dans un environnement Lync Server 2010, Office Communications Server 2007 R2 ou Office Communications Server 2007, voir la <A href="migration.md">migration</A> pour plus d’informations sur la migration vers Lync Server 2013. La migration n’est pas prise en charge dans les versions antérieures à Office Communications Server 2007 R2, y compris Office Communications Server 2007, Live Communications Server 2005 et Live Communications Server 2003.



</div>

Pour améliorer les performances et la sécurité du serveur Edge et faciliter le déploiement, appliquez les meilleures pratiques suivantes lors du déploiement de votre réseau de périmètre et des serveurs Edge :

  - Déployez les serveurs Edge uniquement après avoir testé et vérifié le fonctionnement de Lync Server 2013 au sein de votre organisation.

  - Nous vous recommandons de déployer des serveurs de périphérie dans un groupe de travail plutôt que sur un domaine. Cette opération simplifie l’installation et conserve les services de domaine Active Directory (AD DS) du réseau de périmètre. La recherche d’AD DS dans le réseau de périmètre peut présenter un risque de sécurité considérable.

  - La participation à un serveur Edge vers un domaine situé entièrement dans le réseau de périmètre est prise en charge, mais n’est pas recommandée. Un serveur Edge dans le cadre du domaine interne viole les limites réseau approuvées, où Internet est le moins fiable, le réseau de périmètre est plus fiable qu’Internet et le réseau interne est le plus fiable. Un serveur Edge en tant que membre du domaine fait automatiquement partie du réseau le plus fiable, mais réside dans un réseau moins fiable (le périmètre).

<div>

## <a name="deployment-process-for-edge-servers"></a>Processus de déploiement pour les serveurs de périphérie


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
<th>Documentation</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Créez la topologie de bord appropriée et déterminez les composants appropriés.</p></td>
<td><ul>
<li><p>Exécutez le générateur de topologie pour configurer les paramètres du serveur de bord et créer et publier la topologie, puis utilisez Lync Server Management Shell pour exporter le fichier de configuration de la topologie.</p></li>
</ul></td>
<td><p>Groupe <strong>administrateurs de domaine</strong> et groupe <strong>RTCUniversalServerAdmins</strong> ou <strong>CsAdmins</strong></p>
<div>

> [!NOTE]  
> Vous pouvez définir une topologie à l’aide d’un compte membre du groupe utilisateurs locaux, mais la publication d’une topologie nécessite un compte membre du groupe <STRONG>administrateurs de domaine</STRONG> et du groupe <STRONG>RTCUniversalServerAdmins</STRONG> .


</div></td>
<td><p><a href="lync-server-2013-building-an-edge-and-director-topology.md">Création d’une topologie de périphérie et de réalisateur dans Lync Server 2013</a> dans la documentation de déploiement</p></td>
</tr>
<tr class="even">
<td><p>Préparez-vous à l’installation.</p></td>
<td><ol>
<li><p>Vérifiez que les conditions système préalables sont remplies.</p></li>
<li><p>Configurez les adresses IP (IPv4 et IPv6, s’il est utilisé) pour les interfaces réseau internes et publiques sur chaque serveur Edge.</p></li>
<li><p>Configurez les enregistrements DNS internes et externes (Host A et AAAA pour IPv4 et IPv6), y compris la configuration du suffixe DNS sur l’ordinateur pour être déployé en tant que serveur Edge.</p></li>
<li><p>Facultatif Créez et installez des certificats publics. Le temps requis pour obtenir des certificats dépend de l’autorité de certification qui émet le certificat. Si vous n’effectuez pas cette étape à ce stade, vous devez le faire lors de l’installation du serveur Edge. Les services du serveur Edge ne peuvent pas être démarrés tant que les certificats n’ont pas été obtenus et installés.</p></li>
<li><p>La prise en charge de la connectivité PIC (Public IM Connectivity), si votre déploiement prend en charge les communications avec Windows Live, AOL ou Yahoo ! ont.</p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P>À compter du 1er septembre, 2012, le contrat de licence de l’utilisateur Microsoft Lync Public IM Connectivity (« PIC USL ») ne sera plus disponible à l’achat pour les contrats de nouveau ou de renouvellement. Les clients disposant de licences actives seront en mesure de continuer à fédérer avec Yahoo ! Messenger jusqu’à la date d’arrêt du service. Date de fin de vie du 2014 juin pour AOL et Yahoo ! a été annoncé. Pour plus d’informations, voir <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">prise en charge de la connectivité de messagerie instantanée publique dans Lync Server 2013</A>.</P>
> <LI>
> <P>La fonction USL (PIC) est une licence d’abonnement par mois qui est requise pour que Lync Server ou Office Communications Server se fédérer avec Yahoo ! Messenger. La capacité de Microsoft à fournir ce service est subordonné à la prise en charge de Yahoo !, le contrat sous-jacent pour lequel le son est arrêté.</P>
> <LI>
> <P>Plus que jamais, Lync est un outil puissant de connexion entre organisations et de personnes dans le monde entier. La Fédération avec Windows Live Messenger ne nécessite aucune licence d’utilisateur/appareil supplémentaire au-delà de la CAL standard Lync. Skype Federation sera ajouté à cette liste et permettra aux utilisateurs de Lync de joindre des centaines de millions de personnes à la messagerie instantanée et à la voix.</P></LI></UL>


</div></li>
<li><p>La prise en charge de XMPP et de la prise en charge de la Fédération pour Office Communications Server 2007, Office Communications Server 2007 R2 et les partenaires Lync Server 2010, si votre déploiement utilisera ces</p></li>
<li><p>Configurer des pare-feu.</p></li>
</ol></td>
<td><p>En fonction de votre organisation</p></td>
<td><p><a href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Préparer l’installation des serveurs dans le réseau de périmètre pour Lync Server 2013</a> dans la documentation de déploiement</p></td>
</tr>
<tr class="odd">
<td><p>Configurez un proxy inverse.</p></td>
<td><ul>
<li><p>Configurez le proxy inverse (par exemple, pour la passerelle Microsoft Forefront Threat Management 2010 ou Microsoft Internet Security and Acceleration (ISA) Server avec Service Pack 1) dans le réseau de périmètre, obtenez les certificats publics nécessaires et configurez le règles de publication Web sur le serveur proxy inverse.</p>
<p>Préparez le proxy inverse pour les services de mobilité si vous avez planifié la mobilité et déployez les services de mobilité sur le pool frontal ou le serveur Standard Edition Server.</p></li>
</ul></td>
<td><p>Groupe <strong>administrateurs</strong> ou administrateur de proxy inverse</p></td>
<td><p><a href="lync-server-2013-setting-up-reverse-proxy-servers.md">Configuration de serveurs proxy inverse pour Lync Server 2013</a> dans la documentation de déploiement</p></td>
</tr>
<tr class="even">
<td><p>Configurer un directeur (facultatif).</p></td>
<td><ul>
<li><p>Facultatif Installez et configurez un ou plusieurs directeurs sur le réseau interne.</p></li>
</ul></td>
<td><p>Groupe <strong>administrateurs</strong></p></td>
<td><p><a href="lync-server-2013-setting-up-the-director.md">Configuration du réalisateur dans Lync Server 2013</a> dans la documentation de déploiement</p></td>
</tr>
<tr class="odd">
<td><p>Configurez les serveurs Edge.</p></td>
<td><ol>
<li><p>Installez le logiciel requis.</p></li>
<li><p>Transférez le fichier de configuration topologique exporté vers chaque serveur Edge.</p></li>
<li><p>Installez le logiciel Lync Server 2013 sur chaque serveur Edge.</p></li>
<li><p>Configurez les serveurs de périphérie.</p></li>
<li><p>Demandez et installez des certificats pour chaque serveur Edge.</p></li>
<li><p>Démarrez les services Edge Server.</p></li>
</ol></td>
<td><p>Groupe <strong>administrateurs</strong></p></td>
<td><p><a href="lync-server-2013-setting-up-edge-servers.md">Configuration de serveurs de frontière dans Lync Server 2013</a> dans la documentation de déploiement</p></td>
</tr>
<tr class="even">
<td><p>Configurer le déploiement pour l’accès des utilisateurs externes.</p></td>
<td><ol>
<li><p>Utilisez le panneau de configuration de Lync Server pour configurer la prise en charge de chacun des éléments suivants (selon le cas) :</p>
<ul>
<li><p>Relais multimédia</p></li>
<li><p>Itinéraire de Fédération</p></li>
<li><p>Accès des utilisateurs distants</p></li>
<li><p>Fédération avec Lync Server, Office Communications Server et Live Communications Server</p></li>
<li><p>Solution PIC (Public IM Connectivity)</p></li>
<li><p>Fédération XMPP</p></li>
<li><p>Utilisateurs anonymes</p></li>
</ul></li>
<li><p>Configurer les comptes d’utilisateurs pour l’accès des utilisateurs distants, la Fédération, la connectivité PIC (Public IM Connectivity), le service d’assistance utilisateur (selon le cas)</p></li>
</ol></td>
<td><p><strong>RTCUniversalServerAdmins</strong> groupe ou compte d’utilisateur affecté au rôle <strong>CSAdministrator</strong></p></td>
<td><p><a href="lync-server-2013-configuring-support-for-external-user-access.md">Configuration de la prise en charge de l’accès des utilisateurs externes dans Lync Server 2013</a> dans la documentation de déploiement</p></td>
</tr>
<tr class="odd">
<td><p>Vérifiez la configuration de votre serveur Edge.</p></td>
<td><ol>
<li><p>Vérifier la connectivité du serveur et la réplication des données de configuration à partir de serveurs internes.</p></li>
<li><p>Vérifiez que les utilisateurs externes peuvent se connecter, y compris aux utilisateurs distants, aux utilisateurs des domaines fédérés, aux utilisateurs de messagerie instantanée publique et aux utilisateurs anonymes, en fonction de votre déploiement.</p></li>
<li><p>Vérifier la configuration et la communication à l’aide de Lync Server Remote Connectivity Analyzer<a href="https://www.testocsconnectivity.com" class="uri">https://www.testocsconnectivity.com</a></p></li>
<li><p>Résoudre les problèmes de configuration et de communication</p></li>
</ol></td>
<td><p>Pour la vérification de la réplication, du groupe <strong>RTCUniversalServerAdmins</strong> ou du compte d’utilisateur affecté au rôle <strong>CSAdministrator</strong></p>
<p>Pour la vérification de la connectivité utilisateur, un utilisateur pour chaque type d’accès des utilisateurs externes que vous prenez en charge</p>
<p>Utilisateurs distants</p></td>
<td><p><a href="lync-server-2013-verifying-your-edge-deployment.md">Vérifier votre déploiement Edge dans Lync Server 2013</a> dans la documentation de déploiement</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

