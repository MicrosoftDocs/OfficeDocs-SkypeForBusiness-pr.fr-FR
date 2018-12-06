---
title: 'Lync Server 2013 : Nouveautés pour les clients'
TOCTitle: Nouveautés pour les clients
ms:assetid: 5c144677-4d58-4fc3-8445-74b76c9fcf07
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204933(v=OCS.15)
ms:contentKeyID: 49297335
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Nouveautés pour les clients dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Microsoft Lync 2013 possède une interface utilisateur remaniée et de nouvelles fonctionnalités importantes. Le client est désormais fourni avec le programme d’installation d’Office, offrant aux administrateurs une approche plus rationalisée pour déployer Office et personnaliser des clients dans votre organisation.

> [!NOTE]  
> Pour obtenir une vue illustrée des mises à jour de l’interface utilisateur Lync 2013, reportez-vous à « Nouveautés de Lync 2013 » à l’adresse <a href="http://go.microsoft.com/fwlink/?linkid=273885">http://go.microsoft.com/fwlink/?LinkId=273885</a>.

## Intégration au programme d’installation d’Office

Le client Lync 2013 et le complément de réunion en ligne pour Lync 2013 (qui prend en charge la gestion des réunions depuis le client de messagerie et de collaboration Outlook) sont désormais inclus dans le programme d’installation Office 2013.

Dans les versions précédentes de Lync et d’Office Communicator, vous pouviez utiliser les propriétés de Windows Installer pour personnaliser et contrôler l’installation d’Office. Lync 2013 étant désormais intégré au programme d’installation d’Office, vous pouvez utiliser les méthodes suivantes pour personnaliser l’installation de Lync 2013 :

  - Utiliser l’Outil de personnalisation Office (OPO)

  - Utiliser le fichier Config.xml pour effectuer les tâches d’installation

  - Utiliser les options de ligne de commande du programme d’installation

> [!NOTE]  
> Le programme d’installation de Lync 2013 ne désinstalle pas les versions précédentes de Lync ou d’Office Communicator. Le client Lync 2013 est installé côte à côte avec d’autres clients Lync ou Office Communicator.

Pour plus d’informations, reportez-vous à la section [Déploiement des clients Lync dans Lync Server 2013](lync-server-2013-deploying-lync-clients.md).

## Déploiement de la stratégie de groupe

Lync 2013 étant à présent inclus dans le programme d’installation d’Office, la méthode de déploiement des paramètres de la stratégie de groupe Lync a évolué. Dans les versions précédentes de Lync et d’Office Communicator, vous pouviez utiliser Communicator.adm pour définir des paramètres de stratégie de groupe. En revanche, dans Lync 2013, vous pouvez désormais utiliser les modèles d’administration ADMX et ADML Lync fournis avec les modèles d’administration de la stratégie de groupe Office.

Pour plus d’informations, reportez-vous à la section [Paramètres des stratégies de groupe de Lync 2013](lync-server-2013-group-policy-settings-for-lync-2013.md).

## Mises à jour apportées au complément Planification dans Outlook

Le complément de réunion en ligne pour Lync 2013 permet de personnaliser les invitations à des réunions et offre de nouvelles options de réunion.

  - Les administrateurs ont la possibilité de personnaliser les invitations à des réunions de leur organisation en ajoutant un logo personnalisé, une URL de support technique, une URL d’exclusion de responsabilité ou encore du texte personnalisé dans le pied de page. Pour plus d’informations, reportez-vous à [Personnalisation du complément de réunion en ligne dans Lync Server 2013](lync-server-2013-customizing-the-online-meeting-add-in.md).

  - De nouveaux contrôles de désactivation du son des participants permettent aux organisateurs de réunion de planifier des conférences dans lesquelles l’audio et la vidéo des participants sont désactivés par défaut.

## Plug-in VDI (Virtual Desktop Infrastructure)

Le client Lync 2013 prend désormais en charge l’audio et la vidéo dans un environnement VDI (Virtual Desktop Infrastructure). Un utilisateur peut connecter un périphérique audio ou vidéo (par exemple, un casque ou une caméra) à l’ordinateur local (par exemple, un client léger ou un ordinateur réaffecté). L’utilisateur peut se connecter à l’ordinateur virtuel, se connecter au client Lync 2013 en cours d’exécution sur l’ordinateur virtuel et participer à des communications audio et vidéo en temps réel comme si le client était exécuté localement. Les fonctionnalités suivantes sont prises en charge dans un environnement de bureau virtuel :

  - Intégration de périphériques pour l’audio et la vidéo, notamment :
    
      - Contrôle des appels à partir du périphérique
    
      - Intégration de la présence sur le périphérique
    
      - Prise en charge de plusieurs périphériques d’interface utilisateur (HID)

  - Prise en charge des services de localisation et d’urgence

  - Prise en charge de toutes les modalités de Lync, dont la messagerie instantanée, l’audio, la vidéo, le partage d’application, le partage de Bureau, le partage de PowerPoint, le tableau blanc et le transfert de fichiers

  - Prise en charge de l’audio et de la vidéo dans les appels de personne à personne et les téléconférences

Pour plus d’informations sur le déploiement du plug-in VDI, reportez-vous à [Déploiement du plug-in Lync VDI dans Lync Server 2013](lync-server-2013-deploying-the-lync-vdi-plug-in.md).

## Améliorations apportées à la vidéo

L’ajout de plusieurs nouvelles fonctionnalités a permis d’améliorer sensiblement l’expérience vidéo des participants à des conférences.

  - Grâce aux améliorations apportées telles que la détection du visage et le cadrage actif, la vidéo peut se déplacer pour maintenir le participant au centre du cadre.

  - La vidéo haute définition est désormais prise en charge dans les appels à deux et les conférences à plusieurs. Les utilisateurs peuvent bénéficier de résolutions HD pouvant aller jusqu’à 1080 p.

  - Les participants ont le choix entre différentes dispositions de réunion : la vue Galerie montre l’ensemble des photos ou des vidéos des participants ; la vue Présentateur montre le contenu de la réunion et uniquement la vidéo ou l’image du présentateur actuel ; la vue Présentation montre uniquement le contenu de la réunion ; et la vue Compact montre uniquement les contrôles de la réunion.

  - Grâce à la nouvelle fonctionnalité Galerie, les participants peuvent voir plusieurs flux vidéo en même temps. Si la conférence compte plus de cinq participants, seuls les flux vidéo des participants les plus actifs s’affichent dans la ligne du haut, tandis que des images s’affichent pour les autres participants.

  - Les participants peuvent utiliser l’épinglage vidéo pour sélectionner un ou plusieurs des flux vidéo disponibles et les afficher en permanence.

  - Les présentateurs peuvent utiliser la fonctionnalité de vidéo à la une pour sélectionner le flux vidéo d’une personne. De cette manière, tous les participants à la réunion voient uniquement ce participant.

## Intégration de la salle de conversation

Lync 2013 intègre désormais les fonctionnalités précédemment fournies par Conversation de groupe Lync 2010. Il n’est plus nécessaire de disposer d’un client de conversation de groupe distinct.

  - Dans Lync 2013, les utilisateurs peuvent rechercher des salles de conversation, ajouter des salles de conversation à leurs contacts, surveiller l’activité de la salle de conversation, ainsi que lire et publier des messages.

  - Les utilisateurs peuvent créer des flux de sujets de manière à être informés si quelqu’un dans l’une de leurs salles de conversation ajoute un billet contenant des mots clés spécifiques.

  - Grâce à la nouvelle page d’options **Conversation permanente** , les utilisateurs peuvent définir des alertes de notification et des sons à émettre lorsque des personnes publient des messages dans leurs salles de conversation.

## Mises à jour apportées à Lync Web App

Lync Web App est le client de conférence basé sur le web pour les réunions Lync Server 2013. Dans cette version, l’ajout du protocole voix sur IP et de la vidéo à Lync Web App fournit un environnement de réunion complet pour toute personne qui ne dispose pas d’un client Lync installé localement. Les participants à la réunion ont accès à toutes les fonctionnalités de collaboration et de partage et aux contrôles de réunion du présentateur.

Lorsqu’un utilisateur qui ne dispose pas d’un client installé localement tente de rejoindre une réunion, Lync Web App s’ouvre. Si vous souhaitez autoriser des options supplémentaires pour participer à la réunion, vous pouvez configurer la page de participation à la réunion. Reportez-vous à [Configuration de la page de participation à une réunion dans Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md) dans la documentation de déploiement.

En raison des améliorations apportées à Lync Web App, une version mise à jour d’Participant n’est pas disponible pour Lync Server 2013. Lync Web App est le client de choix pour les participants à l’extérieur de votre organisation. Aucun client local ne doit être installé, même si les fonctionnalités audio, vidéo et de partage nécessitent l’installation d’un plug-in lors de la première utilisation.

## Mises à jour de Lync 2013 pour les clients mobiles

Outre une amélioration des fonctionnalités de présence, de contacts et de messagerie instantanée, les clients mobiles Lync 2013 offrent désormais les fonctionnalités d’appel audio et vidéo via Internet et les connexions de données cellulaires. Il suffit aux utilisateurs mobiles d’appuyer sur le lien d’une réunion dans un élément de calendrier pour participer à une réunion audio et vidéo Lync. Pour plus d’informations sur les clients mobiles Lync 2013, reportez-vous à [Planification des clients mobiles dans Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).

## Mises à jour apportées à l’interface utilisateur de Lync 2013

## Mises à jour apportées à l’accessibilité

Lync 2013 intègre plusieurs nouvelles fonctionnalités d’accessibilité.

  - Lync 2013 prend en charge une résolution élevée, permettant aux utilisateurs de mettre à l’échelle le texte et les graphiques à 125 % et 150 % points par pouce.

  - Lync prend en charge le contraste élevé pour que l’interface utilisateur reste entièrement fonctionnelle lorsque des thèmes à contraste élevé sont utilisés dans Windows.

  - Lync offre plus de 100 raccourcis clavier afin que les utilisateurs puissent accéder aux fonctions importantes sans souris. Par exemple, les utilisateurs peuvent appuyer sur Alt+C pour accepter un appel ou sur Alt+I pour l’ignorer, le tout sans changer d’onglet ou définir le focus. De plus, Alt+Q met fin à un appel, Ctrl+N démarre OneNote et Alt+T ouvre le menu Outils.

  - Grâce à une prise en charge étendue des lecteurs d’écran dans Lync 2013, les notifications, demandes entrantes et messages instantanés sont tous lus à haute voix lorsqu’un lecteur d’écran est activé.

## Présence pendant le partage

Lorsque Lync détecte qu’un utilisateur partage des éléments, Lync affecte automatiquement à l’utilisateur le statut de présence En présentation. Cette situation bloque toutes les communications entrantes, sauf si l’expéditeur est affecté au niveau de confidentialité Groupe de travail. Si l’utilisateur utilise la fonctionnalité de partage entièrement sur un moniteur secondaire, Lync n’affecte pas de statut de présence En présentation.

## Mises à jour apportées à la fenêtre Conversation

Entièrement repensée, la fenêtre Conversation offre un accès rapide aux fonctions importantes.

  - Grâce à la nouvelle fonctionnalité de conversations par onglets, les utilisateurs peuvent à présent avoir l’ensemble de leurs messages instantanés et de leurs salles de conversation dans une seule fenêtre Conversation. Les onglets situés à gauche de la fenêtre Conversation permettent aux utilisateurs de naviguer facilement parmi toutes les conversations actives.

  - Les utilisateurs peuvent détacher une conversation individuelle dans une fenêtre distincte et redimensionner la fenêtre. Ils peuvent aussi faire revenir la fenêtre dans la fenêtre Conversation principale.

  - Lync 2013 rouvre les conversations d’un utilisateur lorsque l’utilisateur se déconnecte et se reconnecte à Lync.

  - Les utilisateurs peuvent rapidement ajouter la messagerie instantanée, la vidéo, le partage de programme, le partage de Bureau ou des outils de conférence web (tableau blanc, notes de réunion, blocs-notes partagés et pièces jointes) à n’importe quelle conversation.

  - Lors d’une réunion dans laquelle la vidéo ou du contenu est partagé, les utilisateurs peuvent détacher la vidéo ou le contenu partagé de la réunion, puis redimensionner la fenêtre.

## Mises à jour apportées à la fenêtre principale de Lync

La nouvelle apparence rationalisée conserve des fonctionnalités familières telles que le champ de note **Activités du jour** , le sélecteur de statut et le sélecteur **Définir votre emplacement** .

  - Lorsque des salles de conversation sont activées, les utilisateurs voient une nouvelle icône **Salles de conversation** dans la page principale de Lync. Avec l’icône **Salles de conversation** , les utilisateurs peuvent accéder rapidement à leurs salles de conversation et à leurs filtres.

  - Les utilisateurs peuvent cliquer sur les icônes de vue pour passer à la vue **Contacts** , **Salles de conversation** , **Conversations** ou **Téléphone** .

  - Si les utilisateurs ont été migrés vers Exchange 2013, ils peuvent télécharger une image en haute résolution.

## Mises à jour apportées à la vue Contacts et aux cartes de visite

Lync 2013 donne aux utilisateurs différentes façons d’afficher les contacts et les groupes dans leur vue **Contacts** .

  - Avec le nouveau magasin de contacts unifié, une fois les contacts Lync des utilisateurs migrés vers Exchange 2013, les utilisateurs peuvent accéder à leurs contacts et les gérer à partir de Lync 2013, d’Outlook ou d’Outlook Web App, et leurs Favoris restent synchronisés. Par exemple, si un utilisateur ajoute un contact aux Favoris dans Outlook, le contact s’affiche dans le groupe Favoris dans Lync 2013.

  - Si vous avez ajouté et configuré le proxy XMPP et la passerelle XMPP, les utilisateurs peuvent ajouter des contacts de partenaires basés sur XMPP pour la messagerie instantanée et la présence.

  - La nouvelle fonctionnalité **Ajouter un contact qui ne fait pas partie de ma société** offre aux utilisateurs un moyen facile d’ajouter des personnes externes à l’organisation.

  - Le nouveau groupe **Favoris** permet aux utilisateurs de créer une liste de personnes qu’ils contactent le plus souvent pour un accès plus rapide.

  - Les utilisateurs peuvent utiliser la nouvelle page d’options **Liste des contacts** pour choisir la façon dont les utilisateurs souhaitent trier et afficher les contacts. Les utilisateurs peuvent sélectionner une vue développée sur deux lignes qui montre les images des contacts ou une vue condensée sur une ligne. Les utilisateurs peuvent également trier les contacts par ordre alphabétique ou par disponibilité.

## Mises à jour apportées aux conférences

Lync 2013 offre plusieurs améliorations aux fonctionnalités de conférence.

  - Selon le type de réunion, les utilisateurs peuvent à présent désactiver le micro de l’audience et autoriser ou bloquer le partage vidéo lors de la planification de la réunion. Ces options sont disponibles dans la page **Options de la réunion** et sont recommandées pour les grandes réunions de plus de 20 participants.

  - Des contrôles audio faciles à utiliser dans la salle de réunion permettent à l’utilisateur de contrôler les options audio, telles que l’activation du micro, la désactivation du micro, le changement de périphérique, etc.

  - Lors du partage de programmes, les utilisateurs peuvent sélectionner plusieurs programmes à partager s’ils ont besoin de travailler avec plus d’un programme.

  - Les utilisateurs peuvent à présent télécharger des présentations qui contiennent des clips vidéo en téléchargeant le fichier PowerPoint et en pointant la souris sur la diapositive pour afficher les contrôles vidéo (tels que Lire et Pause) et audio.

  - Au cours d’une réunion, les utilisateurs peuvent fusionner une autre conversation ouverte dans la réunion en sélectionnant **Fusionner cet appel dans** dans le menu **Autres options** ( **...** ).

  - Pour afficher le nom des participants, les utilisateurs peuvent pointer la souris sur le bouton **Afficher les participants** ou cliquer sur **Afficher la liste des participants** pour ancrer le volet à la réunion.

  - Selon le type de réunion, les utilisateurs ont le choix entre différentes vues du contenu et des participants.

  - Les enregistrements de réunion sont automatiquement enregistrés dans un format compatible avec le Lecteur Windows Media (MP4). Les utilisateurs peuvent facilement partager le fichier avec d’autres personnes ou utiliser la fonctionnalité **Publier** dans le Gestionnaire d’enregistrements pour publier l’enregistrement dans un emplacement partagé.

  - OneNote offre de nouvelles façons de collaborer dans une réunion. Au cours d’une réunion, les utilisateurs peuvent prendre des notes avec OneNote pour un usage personnel après la réunion, ou utiliser des blocs-notes partagés et les modifier en collaboration avec les participants en temps réel. Tous les membres de l’équipe peuvent accéder aux notes partagées pour contribuer aux informations, échanger des idées ou utiliser les pages du bloc-notes comme tableau blanc virtuel. Les personnes et le contenu partagés dans la réunion sont automatiquement ajoutés aux notes.

  - Les utilisateurs peuvent basculer entre les types de contenu à l’aide de l’option **Partager du contenu et mener des activités de réunion** en bas de la salle de réunion. Les utilisateurs peuvent également utiliser le menu **Gérer le contenu à présenter** pour choisir le contenu à partager.

## Voir aussi

#### Autres ressources

[Planification du déploiement des clients dans Lync Server 2013](lync-server-2013-planning-for-clients.md)

