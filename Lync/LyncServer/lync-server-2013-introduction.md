---
title: Présentation de Lync Server 2013
TOCTitle: Présentation de Lync Server
ms:assetid: 99dd6b65-e591-421f-852b-ee9fe9588998
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398795(v=OCS.15)
ms:contentKeyID: 49298312
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Présentation de Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Lync Server 2013 et son logiciel client, tel que Lync 2013, permettent aux utilisateurs de se connecter selon de nouvelles méthodes et de rester connectés, quel que soit leur emplacement physique. Lync et Lync Server rassemblent les différentes façons de communiquer en une seule interface cliente, sont déployés en tant que plateforme unifiée et sont administrés via une infrastructure de gestion unique.

Ce tableau et les sections suivantes illustrent les principaux jeux de fonctionnalités ou *charges de travail* que Lync Server propose aux utilisateurs.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Charge de travail</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Messagerie instantanée et présence</p></td>
<td><p>La messagerie instantanée et la fonction de présence aident les utilisateurs à trouver un interlocuteur et à communiquer avec efficacement.</p>
<p>La messagerie instantanée fournit une plateforme de messagerie instantanée avec un historique des conversations et prend en charge la connectivité PIC (Public IM Connectivity) avec les utilisateurs de réseaux publics de messagerie instantanée, tels que MSN/Windows Live, Yahoo!, AOL et Google Talk.</p>

> [!IMPORTANT]  
> <ul>
> <li><p>Depuis le 1er septembre 2012, la licence Microsoft Lync « PIC USL » (Public IM Connectivity User Subscription License) n’est plus disponible et ne peut pas être achetée ou renouvelée. Les clients disposant de licences actives pourront continuer à assurer la fédération avec Yahoo! Messenger jusqu’à la date d’arrêt du service. Une date de fin de vie de juin 2014 a été annoncée pour AOL et Yahoo! Pour plus d’informations, reportez-vous à <a href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Prise en charge de la connectivité PIC (Public IM Connectivity) dans Lync Server 2013</a>.</p></li>
> <li><p>La licence PIC USL est une licence d’abonnement mensuel par utilisateur requise pour la fédération de Lync Server ou Office Communications Server avec Yahoo! Messenger. La capacité de Microsoft à fournir ce service est liée au soutien de Yahoo!, dont le contrat sous-jacent arrive à expiration.</p></li>
> <li><p>Lync est un outil puissant permettant aux organisations et aux individus du monde entier de rester connectés. La fédération avec Windows Live Messenger ne nécessite aucune licence utilisateur/appareil supplémentaire en plus de la licence d’accès client (CAL) standard Lync. La fédération avec Skype sera prochainement ajoutée à cette liste, ce qui permettra aux utilisateurs Lync d’entrer en contact avec des centaines de millions de personnes à l’aide des fonctionnalités vocales et de messagerie instantanée.</p></li>
> </ul>

<p>La fonction de présence établit et affiche la disponibilité personnelle d’un utilisateur, ainsi que sa volonté à communiquer via l’utilisation de statuts communs tels que <strong>Disponible</strong> ou <strong>Occupé</strong> , ainsi que des statuts plus détaillés tels que <strong>De retour dans quelques minutes</strong> et <strong>Ne pas déranger</strong> . Cette information quant à la présence permet aux autres utilisateurs d’effectuer immédiatement des choix de communication efficaces.</p></td>
</tr>
<tr class="even">
<td><p>Conférence</p></td>
<td><p>Lync Server inclut la prise en charge de conférences par messagerie instantanée, d’audioconférences, de conférences web, de vidéoconférences et de partage d’application à la fois pour les réunions planifiées et imprévues. Tous ces types de réunions sont gérés par un seul client. Lync Server prend également en charge les conférences rendez-vous afin que des utilisateurs de téléphones RTC (réseau téléphonique commuté) puissent participer à la partie audio des conférences.</p>
<p>Les conférences peuvent être modifiées en toute transparence et croître en temps réel. Par exemple, une conférence unique peut démarrer sous forme de simples messages instantanés échangés entre quelques utilisateurs, puis se transformer en une audioconférence avec partage de Bureau et un public plus important instantanément, aisément et sans interrompre le fil de la conversation.</p></td>
</tr>
<tr class="odd">
<td><p>Voix Entreprise</p></td>
<td><p><em>Voix Entreprise</em> correspond au protocole VoIP (protocole voix sur IP) proposé dans Lync Server. Il fournit une option de voix afin d’améliorer et de remplacer les systèmes classiques d’autocommutateurs privés (PBX). Outre la palette complète des fonctionnalités de téléphonie IP PBX, Voix Entreprise comprend des fonctions de présence enrichie, de messagerie instantanée, de collaboration et de réunions. Les fonctions d’appel, telles que réponse, mise en attente, reprise, transfert et redirection, sont directement prises en charge, tandis que les touches personnalisées de numérotation rapide sont remplacées par des listes de contacts et l’interphone automatique par la messagerie instantanée.</p>
<p>Voix Entreprise gère la haute disponibilité via le contrôle d’admission des appels (CAC), le Survivable Branch Appliance et des options étendues pour la résistance des données.</p></td>
</tr>
<tr class="even">
<td><p>Prise en charge d’utilisateurs distants</p></td>
<td><p>Vous pouvez fournir aux utilisateurs actuellement en dehors des pare-feu de votre organisation une connexion à l’ensemble des fonctionnalités de Lync Server en déployant des serveurs appelés <em>serveurs Edge</em> . Ces utilisateurs distants peuvent se connecter à des conférences à l’aide d’un ordinateur personnel équipé de Lync 2013, d’un téléphone ou d’une interface web.</p>
<p>Déployer des serveurs Edge vous permet également de vous <em>fédérer</em> avec des organisations partenaires ou des prestataires. Une relation fédérée permet à vos utilisateurs de placer des utilisateurs fédérés dans leurs listes de contacts, d’échanger des informations de présence et des messages instantanés avec eux et des les inviter à des appels audio, vidéo et des conférences.</p></td>
</tr>
<tr class="odd">
<td><p>Prise en charge des clients mobiles</p></td>
<td><p>En outre, avec les services de mobilité Lync Server, les utilisateurs peuvent accéder aux fonctionnalités Lync lors de l’utilisation d’appareils mobiles Apple iOS, Android, Windows Phone ou Nokia pris en charge et effectuer des activités telles que l’envoi et la réception de messages instantanés, l’affichage de contacts et l’affichage de la présence. Les appareils mobiles prennent également en charge certaines fonctionnalités de Voix Entreprise telles que telles que Cliquez pour rejoindre une conférence, Appel via le bureau, Appel de numéro unique, la messagerie vocale et les appels en absence. Les notifications push sont également prises en charge pour les appareils mobiles qui ne prennent pas en charge les applications exécutées en arrière-plan.</p></td>
</tr>
<tr class="even">
<td><p>Intégration à d’autres produits</p></td>
<td><p>Lync Server s’intègre à plusieurs autres produits pour fournir des avantages supplémentaires aux utilisateurs et administrateurs.</p>
<p>Les outils de réunion sont intégrés à Outlook pour permettre aux organisateurs de planifier une réunion ou de démarrer une conférence improvisée d’un seul clic et faciliter la participation des membres.</p>
<p>Les informations de présence sont intégrées à Outlook et SharePoint.</p>
<p>La messagerie unifiée Exchange fournit plusieurs fonctionnalités d’intégration. Les utilisateurs peuvent voir s’ils ont reçu de nouveaux messages vocaux dans Lync Server. Ils peuvent cliquer sur un bouton de lecture dans le message Outlook pour écouter le courrier vocal ou en afficher une transcription dans le message de notification.</p>
<p>Par ailleurs, l’exécution de Lync Server 2013 avec Exchange 2013 active plusieurs nouvelles fonctionnalités telles qu’un magasin de contact unifié accessible par les clients des deux produits, ainsi que des photos haute résolution pour les contacts stockés dans la base de données Exchange 2013.</p></td>
</tr>
<tr class="odd">
<td><p>Déploiement simple</p></td>
<td><p>Pour vous aider à planifier et déployer vos serveurs et clients, Lync Server fournit le Générateur de topologie.</p>
<p></p>
<p>Générateur de topologie est un composant d’installation de Lync Server. Le Générateur de topologie permet de créer, régler et publier votre topologie planifiée. Il valide également votre topologie avant que vous ne commenciez à installer les serveurs. Si vous installez Lync Server sur différents serveurs, le programme d’installation déploie le serveur selon les indications de la topologie.</p></td>
</tr>
<tr class="even">
<td><p>Gestion simple</p></td>
<td><p>Après avoir déployé Lync Server, vous avez accès aux outils de gestion puissants et simplifiés suivants :</p>
<ul>
<li><p>Gestion de la configuration centralisée, qui vous permet de gérer les modifications de manière centralisée et de les répliquer rapidement dans l’ensemble du déploiement.</p></li>
<li><p>Panneau de configuration Lync Server, une interface utilisateur graphique web destinée aux administrateurs. Grâce à cette interface, les administrateurs de Lync Server peuvent gérer leurs systèmes à partir de tout point du réseau de l’entreprise sans avoir à installer sur leurs ordinateurs des logiciels de gestion spécialisés.</p></li>
<li><p>Outil de gestion en ligne de commande Lync Server Management Shell, basé sur l’interface de ligne de commande Windows PowerShell. Il fournit un vaste jeu de commandes pour administrer tous les aspects du produit et permet aux administrateurs de Lync Server d’automatiser des tâches répétitives à l’aide d’un outil familier.</p></li>
</ul></td>
</tr>
</tbody>
</table>


Alors que les fonctionnalités de messagerie instantanée et de présence sont automatiquement installées dans chaque déploiement de Lync Server, vous pouvez choisir de déployer ou non le service de conférence, Voix Entreprise et l’accès des utilisateurs distants pour adapter le déploiement aux besoins de votre organisation.

## Dans cette section

  - [Messagerie instantanée et présence dans Lync Server 2013](lync-server-2013-im-and-presence.md)

  - [Conférence dans Lync Server 2013](lync-server-2013-conferencing.md)

  - [Voix Entreprise dans Lync Server 2013](lync-server-2013-enterprise-voice.md)

  - [Évolutivité avec Lync Server 2013](lync-server-2013-scalability.md)

