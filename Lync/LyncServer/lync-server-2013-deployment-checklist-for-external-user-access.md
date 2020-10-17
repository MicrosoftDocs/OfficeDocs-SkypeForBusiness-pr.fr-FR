---
title: 'Lync Server 2013 : liste de vérification du déploiement pour l’accès des utilisateurs externes'
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
ms.openlocfilehash: 010d4437f2eb90d596ace15cc392690dba5544d6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522771"
---
# <a name="deployment-checklist-for-external-user-access-in-lync-server-2013"></a>Liste de vérification du déploiement pour l’accès des utilisateurs externes dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-02-04_

Avant de déployer votre réseau de périmètre et d’implémenter la prise en charge pour les utilisateurs externes, vous devez déjà avoir déployé vos serveurs internes Microsoft Lync Server 2013, y compris un pool frontal ou un serveur Standard Edition. Si vous envisagez de déployer les directeurs facultatifs dans votre réseau interne, vous devez également les déployer avant de déployer les serveurs Edge. Pour plus d’informations sur le processus de déploiement de directeur, voir [scénarios pour le directeur dans Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) dans la documentation de planification.

Microsoft Lync Server 2013 inclut des outils permettant de faciliter la planification et le déploiement des serveurs internes et des serveurs Edge. Une fois la topologie finalisée, publiez la définition de topologie qui en résulte dans votre environnement de production. Pour ce faire, vous devez être membre du groupe **Administrateurs du domaine** et du groupe **RTCUniversalServerAdmins**.

  - **Outil**     de planification Office Communications Server 2007 R2 comprenait un outil de planification et un outil de planification Edge que vous pouvez utiliser pour vous aider à concevoir la topologie. Dans Lync Server 2010, ces deux outils ont été combinés en un seul outil de planification doté de fonctionnalités et de fonctionnalités supplémentaires, telles que la collecte du nombre d’utilisateurs planifiés, les exigences de la voix, les types d’accès des utilisateurs externes et les options de Fédération. Par ailleurs, vous pouvez planifier les paramètres réseau de votre infrastructure, tels que les adresses IP, les types d’équilibrage de charge, ainsi que d’autres considérations relatives aux réseaux de périmètre.

  - Générateur de topologies **Topology Builder**     Le générateur de topologies Lync Server 2013 vous permet de définir votre topologie et vos composants. Le générateur de topologie est essentiel pour déployer des serveurs exécutant Lync Server 2013. Le générateur de topologies publie les résultats dans un magasin central de gestion qui est utilisé pour configurer tous les serveurs exécutant Lync Server 2013 dans votre organisation. Vous ne pouvez pas installer Lync Server 2013 sur des serveurs sans utiliser le générateur de topologie.

Si vous avez conçu votre topologie Edge lors de votre processus de planification, y compris l’exécution du générateur de topologies pour définir votre topologie Edge, vous pouvez utiliser ces résultats pour démarrer le déploiement de votre serveur Edge. Si vous n’avez pas terminé la création de votre topologie Edge ou si vous souhaitez modifier les informations que vous avez précédemment spécifiées, vous devez terminer l’exécution du générateur de topologie avant d’effectuer d’autres étapes de déploiement. Pour plus d’informations sur la création de votre topologie, reportez-vous à la rubrique [scénarios pour l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).

Pour plus d’informations sur l’outil de planification et le générateur de topologies, voir [démarrage du processus de planification pour Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) dans la documentation de planification.

Le tableau suivant présente une vue d’ensemble du processus de déploiement des serveurs Edge. Pour passer en revue les décisions de planification qui doivent être prises avant de déployer l’accès des utilisateurs externes, reportez-vous à la rubrique [scénarios pour l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).

<div>


> [!WARNING]  
> Les informations contenues dans le tableau suivant s’appliquent essentiellement à un nouveau déploiement. Si vous avez déployé des serveurs Edge dans un environnement Lync Server 2010, Office Communications Server 2007 R2 ou Office Communications Server 2007, consultez la rubrique <A href="migration.md">migration</A> pour plus d’informations sur la migration vers Lync Server 2013. La migration n’est pas prise en charge dans les versions antérieures à Office Communications Server 2007 R2, notamment Office Communications Server 2007, Live Communications Server 2005 et Live Communications Server 2003.



</div>

Pour améliorer les performances et le niveau de sécurité des serveurs Edge, mais aussi pour faciliter leur déploiement, appliquez les recommandations suivantes lors du déploiement de votre réseau de périmètre et de vos serveurs Edge :

  - Déployez les serveurs Edge uniquement après avoir testé et vérifié le fonctionnement de Lync Server 2013 au sein de votre organisation.

  - Nous vous recommandons de déployer des serveurs Edge dans un groupe de travail et non pas dans un domaine. Cela simplifie l’installation et conserve les services AD DS (Active Directory Domain Services) en dehors du périmètre du réseau. Leur localisation peut en effet présenter des risques de sécurité importants.

  - L’association d’un serveur Edge Server à un domaine se trouvant entièrement dans le périmètre du réseau est prise en charge, mais non recommandée. Un serveur Edge qui fait partie intégrante du domaine interne enfreint les limites du réseau fiable. En termes de fiabilité, Internet se situe au plus bas de l’échelle, suivi des réseaux de périmètre, puis du réseau interne, qui est considéré comme le plus fiable. Un serveur Edge qui est membre du domaine fait automatiquement partie intégrante du réseau le plus fiable, mais réside dans un réseau moins fiable (le périmètre).

<div>

## <a name="deployment-process-for-edge-servers"></a>Processus de déploiement des serveurs Edge


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
<td><p>Créez la topologie Edge appropriée et déterminez les composants adéquats.</p></td>
<td><ul>
<li><p>Exécutez le générateur de topologie pour configurer les paramètres du serveur Edge et créer et publier la topologie, puis utilisez Lync Server Management Shell pour exporter le fichier de configuration de topologie.</p></li>
</ul></td>
<td><p>Groupe <strong>administrateurs du domaine</strong> et groupe <strong>RTCUniversalServerAdmins</strong> ou <strong>CsAdmins</strong></p>
<div>

> [!NOTE]  
> Vous pouvez définir une topologie à l’aide d’un compte qui est membre du groupe d’utilisateurs locaux, mais la publication d’une topologie nécessite un compte qui soit membre du groupe <STRONG>Administrateurs du domaine</STRONG> et du groupe <STRONG>RTCUniversalServerAdmins</STRONG>.


</div></td>
<td><p><a href="lync-server-2013-building-an-edge-and-director-topology.md">Création d’une topologie de serveur Edge et de directeur dans Lync Server 2013</a> dans la documentation de déploiement</p></td>
</tr>
<tr class="even">
<td><p>Préparez l’installation.</p></td>
<td><ol>
<li><p>Assurez-vous que les conditions préalables du système sont respectées.</p></li>
<li><p>Configurez les adresses IP (IPv4 et IPv6, le cas échéant) des interfaces réseau interne et publique sur chaque serveur Edge.</p></li>
<li><p>Configurez les enregistrements DNS internes et externes (hôte A et AAAA pour IPv4 et IPv6), y compris le suffixe DNS sur l’ordinateur à déployer en tant que serveur Edge.</p></li>
<li><p>(Facultatif) Créez et installez des certificats publics. La durée nécessaire à l’obtention de certificats dépend de l’autorité de certification qui les émet. Si vous n’effectuez pas cette étape à ce stade, vous devrez le faire lors de l’installation du serveur Edge. Les services du serveur Edge ne peuvent pas être démarrés tant que les certificats n’ont pas été obtenus et installés.</p></li>
<li><p>Provisionnez la prise en charge de la solution PIC (Public IM Connectivity) si votre déploiement doit prendre en charge les communications avec des utilisateurs Windows Live, AOL ou Yahoo!.</p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P>À partir du 2012 1er septembre, la licence d’abonnement utilisateur Microsoft Lync Public IM Connectivity (« PIC USL ») n’est plus disponible à l’achat pour les contrats de nouveau ou de renouvellement. Les clients disposant de licences actives seront en mesure de continuer à fédérer avec Yahoo !. Messenger jusqu’à la date d’arrêt du service. Date de fin du 2014 juin pour AOL et Yahoo ! a été annoncé. Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">prise en charge de la connectivité PIC de messagerie instantanée dans Lync Server 2013</A>.</P>
> <LI>
> <P>La fonction USL PIC est une licence d’abonnement par utilisateur et par mois requise pour que Lync Server ou Office Communications Server se fédérer avec Yahoo ! Messenger. La capacité de Microsoft à fournir ce service est subordonnée à la prise en charge de Yahoo !, l’accord sous-jacent de qui est en panne.</P>
> <LI>
> <P>Plus que jamais, Lync est un outil puissant pour la connexion entre les organisations et les utilisateurs dans le monde entier. La Fédération avec Windows Live Messenger ne requiert aucune licence utilisateur/périphérique supplémentaire au-delà de la licence d’accès client Lync standard. La Fédération Skype est ajoutée à cette liste, ce qui permet aux utilisateurs de Lync d’atteindre des centaines de millions de personnes avec la messagerie instantanée et la voix.</P></LI></UL>


</div></li>
<li><p>Mise en service de la prise en charge de XMPP et de la Fédération pour Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 Partners, si votre déploiement utilise ces</p></li>
<li><p>Configurez les pare-feu.</p></li>
</ol></td>
<td><p>En fonction de votre organisation</p></td>
<td><p><a href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Préparation de l’installation des serveurs dans le réseau de périmètre pour Lync Server 2013</a> dans la documentation de déploiement</p></td>
</tr>
<tr class="odd">
<td><p>Installez le proxy inverse.</p></td>
<td><ul>
<li><p>Configurez le proxy inverse (par exemple, pour Microsoft Forefront Threat Management Gateway 2010 ou Microsoft Internet Security and Acceleration (ISA) Server avec Service Pack 1) dans le réseau de périmètre, obtenez les certificats publics nécessaires et configurez les règles de publication Web sur le serveur proxy inverse.</p>
<p>Préparez le proxy inverse pour les services de mobilité si vous avez prévu de les déployer sur le pool frontal ou le serveur Standard Edition.</p></li>
</ul></td>
<td><p>Groupe <strong>Administrateurs</strong> ou administrateur du proxy inverse</p></td>
<td><p><a href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up proxy inverse Servers for Lync Server 2013</a> dans la documentation de déploiement</p></td>
</tr>
<tr class="even">
<td><p>Installez un directeur (facultatif).</p></td>
<td><ul>
<li><p>(Facultatif) Installez et configurez un ou plusieurs directeurs dans le réseau interne.</p></li>
</ul></td>
<td><p>Groupe <strong>Administrateurs</strong></p></td>
<td><p><a href="lync-server-2013-setting-up-the-director.md">Configuration du directeur dans Lync Server 2013</a> dans la documentation de déploiement</p></td>
</tr>
<tr class="odd">
<td><p>Installez des serveurs Edge.</p></td>
<td><ol>
<li><p>Installez les logiciels prérequis.</p></li>
<li><p>Transportez le fichier de configuration de topologie exporté vers chaque serveur Edge.</p></li>
<li><p>Installez le logiciel Lync Server 2013 sur chaque serveur Edge.</p></li>
<li><p>Configurez les serveurs Edge.</p></li>
<li><p>Demandez et installez des certificats pour chaque serveur Edge.</p></li>
<li><p>Démarrez les services du serveur Edge.</p></li>
</ol></td>
<td><p>Groupe <strong>Administrateurs</strong></p></td>
<td><p><a href="lync-server-2013-setting-up-edge-servers.md">Setting up Edge servers in Lync Server 2013</a> dans la documentation de déploiement</p></td>
</tr>
<tr class="even">
<td><p>Configurez le déploiement pour l’accès des utilisateurs externes.</p></td>
<td><ol>
<li><p>Utilisez le panneau de configuration Lync Server pour configurer la prise en charge de chacune des opérations suivantes (selon les cas) :</p>
<ul>
<li><p>Serveur relais multimédia</p></li>
<li><p>Itinéraire de fédération</p></li>
<li><p>Accès des utilisateurs distants</p></li>
<li><p>Fédération avec Lync Server, Office Communications Server et Live Communications Server</p></li>
<li><p>Solution PIC (Public IM Connectivity)</p></li>
<li><p>Fédération XMPP</p></li>
<li><p>Utilisateurs anonymes</p></li>
</ul></li>
<li><p>Configurez les comptes d’utilisateurs pour la prise en charge de l’accès des utilisateurs distants, de la fédération, de la solution PIC (Public IM Connectivity) et des utilisateurs XMPP et anonymes (le cas échéant).</p></li>
</ol></td>
<td><p>Groupe <strong>RTCUniversalServerAdmins</strong> ou compte d’utilisateur affecté au rôle <strong>CSAdministrator</strong></p></td>
<td><p><a href="lync-server-2013-configuring-support-for-external-user-access.md">Configuration de la prise en charge de l’accès des utilisateurs externes dans Lync Server 2013</a> dans la documentation de déploiement</p></td>
</tr>
<tr class="odd">
<td><p>Vérifiez votre configuration de serveur Edge.</p></td>
<td><ol>
<li><p>Vérifiez la connectivité serveur et la réplication des données de configuration à partir des serveurs internes.</p></li>
<li><p>Vérifiez que les utilisateurs externes peuvent se connecter, y compris les utilisateurs distants, les utilisateurs des domaines fédérés, les utilisateurs Public IM et les utilisateurs anonymes, selon votre type de déploiement.</p></li>
<li><p>Vérifier la configuration et la communication à l’aide de l’analyseur de connectivité à distance Lync Server <a href="https://www.testocsconnectivity.com" class="uri">https://www.testocsconnectivity.com</a></p></li>
<li><p>Résoudre les problèmes de configuration et de communication</p></li>
</ol></td>
<td><p>Pour la vérification de la réplication, groupe <strong>RTCUniversalServerAdmins</strong> ou compte d’utilisateur affecté au rôle <strong>CSAdministrator</strong></p>
<p>Pour la vérification de la connectivité utilisateur, un utilisateur pour chaque type d’accès des utilisateurs externes que vous prenez en charge</p>
<p>Utilisateurs distants</p></td>
<td><p><a href="lync-server-2013-verifying-your-edge-deployment.md">Vérification de votre déploiement Edge dans Lync Server 2013</a> dans la documentation de déploiement</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

