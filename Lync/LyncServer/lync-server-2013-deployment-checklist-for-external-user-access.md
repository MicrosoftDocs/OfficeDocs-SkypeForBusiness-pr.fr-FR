---
title: "Lync Server 2013 : Liste de vérif. du dépl. pour l’accès des ut. externes"
TOCTitle: Liste de vérification du déploiement pour l’accès des utilisateurs externes
ms:assetid: 3f55f502-88a0-4315-8783-45a32a0b78ea
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg425910(v=OCS.15)
ms:contentKeyID: 49296996
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Liste de vérification du déploiement pour l’accès des utilisateurs externes dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Avant de déployer votre réseau de périmètre et d’implémenter la prise en charge des utilisateurs externes, vous devez déjà avoir déployé vos serveurs internes Microsoft Lync Server 2013, dont un pool de serveurs frontaux ou un serveur Standard Edition. Si vous prévoyez de déployer des directeurs facultatifs dans votre réseau interne, vous devez aussi les déployer avant les serveurs Edge. Pour plus d’informations sur le processus de déploiement d’un directeur, reportez-vous à [Scénarios pour le directeur dans Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) dans la documentation de planification.

Microsoft Lync Server 2013 intègre des outils qui vous aident à planifier et déployer les serveurs internes et les serveurs Edge. Une fois la topologie finalisée, publiez la définition de topologie qui en résulte dans votre environnement de production. Pour ce faire, vous devez être membre du groupe **Administrateurs du domaine** et du groupe **RTCUniversalServerAdmins**.

  - **Outil de planification** : Office Communications Server 2007 R2 intégrait un outil de planification et un outil de planification Edge que vous pouviez utiliser pour concevoir votre topologie. Dans Lync Server 2010, ces deux outils ont été regroupés dans un même outil de planification qui propose des fonctionnalités supplémentaires, telles que la collecte du nombre prévu d’utilisateurs, des exigences sur le plan de la voix, des types d’accès pour les utilisateurs externes, ainsi que des options de fédération. Par ailleurs, vous pouvez planifier les paramètres réseau de votre infrastructure, tels que les adresses IP, les types d’équilibrage de charge, ainsi que d’autres considérations relatives aux réseaux de périmètre.

  - **Générateur de topologie** : le Générateur de topologieLync Server 2013 vous aide à définir votre topologie et vos composants. Le Générateur de topologie est indispensable pour déployer des serveurs exécutant Lync Server 2013. Le Générateur de topologie publie les résultats dans un magasin central de gestion qui sert à configurer tous les serveurs exécutant Lync Server 2013 dans votre organisation. Vous ne pouvez pas installer Lync Server 2013 sur des serveurs sans utiliser le Générateur de topologie.

Si vous avez conçu votre topologie Edge lors de votre processus de planification en ayant notamment exécuté le Générateur de topologie pour définir votre topologie Edge, vous pouvez utiliser ces résultats pour entamer le déploiement de votre serveur Edge. Si la création de votre topologie Edge n’est pas terminée ou si vous souhaitez modifier les informations définies antérieurement, vous devez terminer l’exécution du Générateur de topologie avant de passer aux autres étapes du déploiement. Pour plus d’informations sur la façon de créer votre topologie, reportez-vous à [Scénarios d’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).

Pour plus d’informations sur l’outil de planification et le générateur de topologie, reportez-vous à [Début du processus de planification pour Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) dans la documentation de planification.

Le tableau ci-dessous présente une vue d’ensemble du processus de déploiement des serveurs Edge. Pour consulter les décisions de planification qui doivent être prises avant de déployer l’accès des utilisateurs externes, reportez-vous à [Scénarios d’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).

> [!WARNING]  
> Les informations contenues dans le tableau suivant s’appliquent essentiellement à un nouveau déploiement. Si vous avez déployé des serveurs Edge dans un environnement Lync Server 2010, Office Communications Server 2007 R2 ou Office Communications Server 2007, reportez-vous à <a href="migration.md">Migration</a> pour plus d’informations sur la migration vers Lync Server 2013. La migration n’est pas prise en charge pour les versions antérieures à Office Communications Server 2007 R2, dont Office Communications Server 2007, Live Communications Server 2005 et Live Communications Server 2003.

Pour améliorer les performances et le niveau de sécurité des serveurs Edge, mais aussi pour faciliter leur déploiement, appliquez les recommandations suivantes lors du déploiement de votre réseau de périmètre et de vos serveurs Edge :

  - Déployez les serveurs Edge uniquement après avoir testé et vérifié le fonctionnement du Lync Server 2013 dans votre organisation.

  - Nous vous recommandons de déployer des serveurs Edge dans un groupe de travail et non pas dans un domaine. Cela simplifie l’installation et conserve les services AD DS (Active Directory Domain Services) en dehors du périmètre du réseau. Leur localisation peut en effet présenter des risques de sécurité importants.

  - L’association d’un serveur Edge Server à un domaine se trouvant entièrement dans le périmètre du réseau est prise en charge, mais non recommandée. Un serveur Edge qui fait partie intégrante du domaine interne enfreint les limites du réseau fiable. En termes de fiabilité, Internet se situe au plus bas de l’échelle, suivi des réseaux de périmètre, puis du réseau interne, considéré comme le plus fiable. Un serveur Edge qui est membre du domaine fait automatiquement partie intégrante du réseau le plus fiable, mais se trouve dans un réseau moins fiable (le périmètre).

## Processus de déploiement des serveurs Edge


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
<td><ul><li><p>Exécutez le Générateur de topologie pour configurer les paramètres de serveur Edge et créez et publiez la topologie, puis utilisez Lync Server Management Shell pour exporter le fichier de configuration de topologie.</p></li></ul>
<p></p></td>
<td><p>Groupe <strong>Administrateurs du domaine</strong> et groupe <strong>RTCUniversalServerAdmins</strong> ou <strong>CsAdmins</strong></p>
<div>

> [!NOTE]  
> Vous pouvez définir une topologie à l’aide d’un compte qui est membre du groupe d’utilisateurs locaux, mais la publication d’une topologie nécessite un compte qui soit membre du groupe <strong>Administrateurs du domaine</strong> et du groupe <strong>RTCUniversalServerAdmins</strong>.
</div></td>
<td><p><a href="lync-server-2013-building-an-edge-and-director-topology.md">Création d’une topologie de serveurs Edge et directeurs dans Lync Server 2013</a> dans la documentation de déploiement</p></td>
</tr>
<tr class="even">
<td><p>Préparez l’installation.</p></td>
<td><ol><li><p>Assurez-vous que les conditions préalables du système sont respectées.</p></li><li><p>Configurez les adresses IP (IPv4 et IPv6, le cas échéant) des interfaces réseau interne et publique sur chaque serveur Edge.</p></li><li><p>Configurez les enregistrements DNS internes et externes (hôte A et AAAA pour IPv4 et IPv6), dont le suffixe DNS sur l’ordinateur à déployer en tant que serveur Edge.</p></li><li><p>(Facultatif) Créez et installez des certificats publics. La durée nécessaire à l’obtention de certificats dépend de l’autorité de certification qui les émet. Si vous n’effectuez pas cette étape à ce stade, vous devrez le faire lors de l’installation du serveur Edge. Les services du serveur Edge ne peuvent pas être démarrés tant que les certificats n’ont pas été obtenus et installés.</p></li><li><p>Provisionnez la prise en charge de la solution PIC (Public IM Connectivity) si votre déploiement doit prendre en charge les communications avec des utilisateurs Windows Live, AOL ou Yahoo!.</p>
<div>

> [!IMPORTANT]  
> <ul>
> <li><p>Depuis le 1er septembre 2012, la licence Microsoft Lync « PIC USL » (Public IM Connectivity User Subscription License) n’est plus disponible et ne peut pas être achetée ou renouvelée. Les clients disposant de licences actives pourront continuer à assurer la fédération avec Yahoo! Messenger jusqu’à la date d’arrêt du service. Une date de fin de vie de juin 2014 a été annoncée pour AOL et Yahoo! Pour plus d’informations, reportez-vous à <a href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Prise en charge de la connectivité PIC (Public IM Connectivity) dans Lync Server 2013</a>.</p></li>
> <li><p>La licence PIC USL est une licence d’abonnement mensuel par utilisateur requise pour la fédération de Lync Server ou Office Communications Server avec Yahoo! Messenger. La capacité de Microsoft à fournir ce service est liée au soutien de Yahoo!, dont le contrat sous-jacent arrive à expiration.</p></li>
> <li><p>Lync est un outil puissant permettant aux organisations et aux individus du monde entier de rester connectés. La fédération avec Windows Live Messenger ne nécessite aucune licence utilisateur/appareil supplémentaire en plus de la licence d’accès client (CAL) standard Lync. La fédération avec Skype sera prochainement ajoutée à cette liste, ce qui permettra aux utilisateurs Lync d’entrer en contact avec des centaines de millions de personnes à l’aide des fonctionnalités vocales et de messagerie instantanée.</p></li></ul>

</div></li><li><p>Configurez la prise en charge du protocole XMPP et de la fédération pour les partenaires Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 si leur utilisation est prévue dans le cadre de votre déploiement.</p></li><li><p>Configurez les pare-feu.</p></li></ol></td>
<td><p>En fonction de votre organisation</p></td>
<td><p><a href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Préparation de l’installation des serveurs sur le réseau de périmètre pour Lync Server 2013</a> dans la documentation de déploiement</p></td>
</tr>
<tr class="odd">
<td><p>Installez le proxy inverse.</p></td>
<td><ul><li><p>Installez le proxy inverse (par exemple, pour Microsoft Forefront Threat Management Gateway 2010 ou Microsoft Internet Security and Acceleration (ISA) Server avec Service Pack 1) dans le réseau de périmètre, obtenez les certificats publics nécessaires, puis configurez les règles de publication web sur le serveur de proxy inverse.</p>
<p>Préparez le proxy inverse pour les services de mobilité si vous avez prévu de les déployer sur le pool frontal ou le serveur Standard Edition.</p></li></ul></td>
<td><p>Groupe <strong>Administrateurs</strong> ou administrateur du proxy inverse</p></td>
<td><p></p>
<p><a href="lync-server-2013-setting-up-reverse-proxy-servers.md">Configuration des serveurs proxy inverses pour Lync Server 2013</a> dans la documentation de déploiement</p></td>
</tr>
<tr class="even">
<td><p>Installez un directeur (facultatif).</p></td>
<td><ul><li><p>(Facultatif) Installez et configurez un ou plusieurs directeurs dans le réseau interne.</p></li></ul></td>
<td><p>Groupe <strong>Administrateurs</strong></p></td>
<td><p><a href="lync-server-2013-setting-up-the-director.md">Configuration du directeur dans Lync Server 2013</a> dans la documentation de déploiement</p></td>
</tr>
<tr class="odd">
<td><p>Installez des serveurs Edge.</p></td>
<td><ol><li><p>Installez les logiciels prérequis.</p></li><li><p>Transportez le fichier de configuration de topologie exporté vers chaque serveur Edge.</p></li><li><p>Installez le logiciel Lync Server 2013 sur chaque serveur Edge.</p></li><li><p>Configurez les serveurs Edge.</p></li><li><p>Demandez et installez des certificats pour chaque serveur Edge.</p></li><li><p>Démarrez les services du serveur Edge.</p></li></ol></td>
<td><p>Groupe <strong>Administrateurs</strong></p></td>
<td><p><a href="lync-server-2013-setting-up-edge-servers.md">Configuration des serveurs Edge dans Lync Server 2013</a> dans la documentation de déploiement</p></td>
</tr>
<tr class="even">
<td><p>Configurez le déploiement pour l’accès des utilisateurs externes.</p></td>
<td><ol><li><p>Utilisez le Panneau de configuration Lync Server pour configurer la prise en charge de chacun des éléments suivants (le cas échéant) :</p><ul><li><p>Serveur relais multimédia</p></li><li><p>Itinéraire de fédération</p></li><li><p>Accès des utilisateurs distants</p></li><li><p>Fédération avec Lync Server, Office Communications Server et Live Communications Server</p></li><li><p>Solution PIC (Public IM Connectivity)</p></li><li><p>Fédération XMPP</p></li><li><p>Utilisateurs anonymes</p></li></ul></li><li><p>Configurez les comptes d’utilisateur pour la prise en charge de l’accès des utilisateurs distants, de la fédération, de la solution PIC (Public IM Connectivity) et des utilisateurs XMPP et anonymes (le cas échéant).</p></li></ol></td>
<td><p>Groupe <strong>RTCUniversalServerAdmins</strong> ou compte d’utilisateur affecté au rôle <strong>CSAdministrator</strong></p>
<p></p></td>
<td><p><a href="lync-server-2013-configuring-support-for-external-user-access.md">Configuration de la prise en charge de l’accès des utilisateurs externes dans Lync Server 2013</a> dans la documentation de déploiement</p></td>
</tr>
<tr class="odd">
<td><p>Vérifiez votre configuration de serveur Edge.</p></td>
<td><ol><li><p>Vérifiez la connectivité serveur et la réplication des données de configuration à partir des serveurs internes.</p></li><li><p>Vérifiez que les utilisateurs externes peuvent se connecter, dont les utilisateurs distants, les utilisateurs des domaines fédérés, les utilisateurs Public IM et les utilisateurs anonymes, selon votre type de déploiement.</p></li><li><p>Vérifiez la configuration et la communication à l’aide de l’analyseur de connectivité à distance Lync Server <a href="https://www.testocsconnectivity.com/" class="uri">https://www.testocsconnectivity.com/</a></p></li><li><p>Résoudre les problèmes de configuration et de communication</p></li></ol></td>
<td><p>Pour la vérification de la réplication, groupe <strong>RTCUniversalServerAdmins</strong> ou compte d’utilisateur affecté au rôle <strong>CSAdministrator</strong></p>
<p>Pour la vérification de la connectivité utilisateur, un utilisateur pour chaque type d’accès des utilisateurs externes que vous prenez en charge</p>
<p>Utilisateurs distants</p></td>
<td><p><a href="lync-server-2013-verifying-your-edge-deployment.md">Vérification de votre déploiement Edge dans Lync Server 2013</a> dans la documentation de déploiement</p></td>
</tr>
</tbody>
</table>

