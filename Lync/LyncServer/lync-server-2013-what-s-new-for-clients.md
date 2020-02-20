---
title: 'Lync Server 2013 : nouveautés pour les clients'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: What's new for clients
ms:assetid: 5c144677-4d58-4fc3-8445-74b76c9fcf07
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204933(v=OCS.15)
ms:contentKeyID: 48184253
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9035ace6a3cfbb65c8effb786bcd6a7568f92252
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149103"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="whats-new-for-clients-in-lync-server-2013"></a>Nouveautés pour les clients dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-19_

Microsoft Lync 2013 dispose d’une interface utilisateur repensée et de nouvelles fonctionnalités importantes. Pour les administrateurs, le client est désormais inclus dans le programme d’installation d’Office, ce qui offre une approche plus rationalisée pour le déploiement d’Office et la personnalisation des clients au sein de votre organisation.

<div>


> [!NOTE]  
> Pour obtenir une vue d’ensemble des mises à jour de l’interface utilisateur de Lync 2013, voir « What’s New in <A href="https://go.microsoft.com/fwlink/?linkid=273885">https://go.microsoft.com/fwlink/?LinkId=273885</A>Lync 2013 » à l’adresse.



</div>

<div>

## <a name="integration-with-office-setup"></a>Intégration au programme d’installation d’Office

Le client Lync 2013 et le complément de réunion en ligne pour Lync 2013, qui prend en charge la gestion des réunions à partir du client de messagerie et de collaboration Outlook, sont désormais inclus dans le programme d’installation d’Office 2013.

Dans les versions précédentes de Lync et Office Communicator, vous pouviez utiliser les propriétés de Windows Installer pour personnaliser et contrôler l’installation d’Office. Étant donné que Lync 2013 est intégré au programme d’installation d’Office, vous pouvez utiliser les méthodes suivantes pour personnaliser le programme d’installation de Lync 2013 :

  - Utiliser l’Outil de personnalisation Office (OPO)

  - Utiliser le fichier Config.xml pour effectuer les tâches d’installation

  - Utiliser les options de ligne de commande du programme d’installation

<div>


> [!NOTE]  
> Le programme d’installation de Lync 2013 ne désinstalle pas les versions précédentes de Lync ou d’Office Communicator. Le client Lync 2013 installe côte à côte avec d’autres clients Lync ou Office Communicator



</div>

Pour plus d’informations, reportez-vous à la rubrique [Deploying Lync clients in Lync Server 2013](lync-server-2013-deploying-lync-clients.md).

</div>

<div>

## <a name="group-policy-deployment"></a>Déploiement de la stratégie de groupe

Étant donné que Lync 2013 est désormais inclus dans le programme d’installation d’Office, la méthode de déploiement des paramètres de stratégie de groupe Lync a changé. Dans les versions précédentes de Lync et Office Communicator, vous pouviez utiliser Communicator. adm pour définir les paramètres de la stratégie de groupe, tandis que dans Lync 2013 vous pouvez désormais utiliser les modèles d’administration Lync ADMX et ADML fournis avec la stratégie de groupe Office. Modèles d’administration.

Pour plus d’informations, consultez la rubrique [paramètres de stratégie de groupe pour Lync 2013](lync-server-2013-group-policy-settings-for-lync-2013.md).

</div>

<div>

## <a name="outlook-scheduling-add-in-updates"></a>Mises à jour apportées au complément Planification dans Outlook

Le complément de réunion en ligne pour Lync 2013 inclut une personnalisation des invitations aux réunions et de nouvelles options de réunion.

  - Les administrateurs ont la possibilité de personnaliser les invitations à des réunions de leur organisation en ajoutant un logo personnalisé, une URL de support technique, une URL d’exclusion de responsabilité ou encore du texte personnalisé dans le pied de page. Pour plus d’informations, reportez-vous à [la rubrique Customizing the online Meeting Add-in in Lync Server 2013](lync-server-2013-customizing-the-online-meeting-add-in.md).

  - De nouveaux contrôles de désactivation du son des participants permettent aux organisateurs de réunion de planifier des conférences dans lesquelles l’audio et la vidéo des participants sont désactivés par défaut.

</div>

<div>

## <a name="virtual-desktop-infrastructure-plug-in"></a>Plug-in VDI (Virtual Desktop Infrastructure)

Le client Lync 2013 prend désormais en charge les fonctionnalités audio et vidéo dans un environnement VDI (Virtual Desktop Infrastructure). Un utilisateur peut connecter un périphérique audio ou vidéo (par exemple, un casque ou une caméra) à l’ordinateur local (par exemple, un client léger ou un ordinateur réaffecté). L’utilisateur peut se connecter à la machine virtuelle, se connecter au client Lync 2013 qui est en cours d’exécution sur l’ordinateur virtuel et participer à la communication audio et vidéo en temps réel comme si le client était en cours d’exécution localement. Les fonctionnalités suivantes sont prises en charge dans un environnement de bureau virtuel :

  - Intégration de périphériques pour l’audio et la vidéo, notamment :
    
      - Contrôle des appels à partir du périphérique
    
      - Intégration de la présence sur le périphérique
    
      - Prise en charge de plusieurs périphériques d’interface utilisateur (HID)

  - Prise en charge des services de localisation et d’urgence

  - Prise en charge de toutes les modalités de Lync, y compris la messagerie instantanée, l’audio, la vidéo, le partage d’applications, le partage de bureau, le partage PowerPoint, le tableau blanc et le transfert de fichiers.

  - Prise en charge de l’audio et de la vidéo dans les appels de personne à personne et les téléconférences

Pour plus d’informations sur le déploiement du plug-in VDI, reportez-vous à [la rubrique Deploying the LYNC VDI plug-in in Lync Server 2013](lync-server-2013-deploying-the-lync-vdi-plug-in.md).

</div>

<div>

## <a name="video-enhancements"></a>Améliorations apportées à la vidéo

L’ajout de plusieurs nouvelles fonctionnalités a permis d’améliorer sensiblement l’expérience vidéo des participants à des conférences.

  - Grâce aux améliorations apportées telles que la détection du visage et le cadrage actif, la vidéo peut se déplacer pour maintenir le participant au centre du cadre.

  - La vidéo haute définition est désormais prise en charge dans les appels à deux et les conférences à plusieurs. Les utilisateurs peuvent bénéficier de résolutions HD pouvant aller jusqu’à 1080 p.

  - Les participants ont le choix entre différentes dispositions de réunion : la vue Galerie montre l’ensemble des photos ou des vidéos des participants ; la vue Présentateur montre le contenu de la réunion et uniquement la vidéo ou l’image du présentateur actuel ; la vue Présentation montre uniquement le contenu de la réunion ; et la vue Compact montre uniquement les contrôles de la réunion.

  - Grâce à la nouvelle fonctionnalité Galerie, les participants peuvent voir plusieurs flux vidéo en même temps. Si la conférence compte plus de cinq participants, seuls les flux vidéo des participants les plus actifs apparaissent dans la ligne du haut, tandis que des images s’affichent pour les autres participants.

  - Les participants peuvent utiliser l’épinglage vidéo pour sélectionner un ou plusieurs des flux vidéo disponibles et les afficher en permanence.

  - Les présentateurs peuvent utiliser la fonctionnalité de vidéo à la une pour sélectionner le flux vidéo d’une personne. De cette manière, tous les participants à la réunion voient uniquement ce participant.

</div>

<div>

## <a name="chat-room-integration"></a>Intégration de la salle de conversation

Lync 2013 intègre désormais les fonctionnalités fournies précédemment par Lync 2010 Group chat. Il n’est plus nécessaire de disposer d’un client de conversation de groupe séparé.

  - À partir de Lync 2013, les utilisateurs peuvent rechercher des salles de conversation, ajouter des salles de conversation à leurs contacts, surveiller l’activité des salles de conversation, ainsi que lire et publier des messages.

  - Les utilisateurs peuvent créer des flux de sujets de manière à être informés si quelqu’un dans l’une de leurs salles de conversation ajoute un billet contenant des mots clés spécifiques.

  - Grâce à la nouvelle page d’options **Conversation permanente**, les utilisateurs peuvent définir des alertes de notification et des sons à émettre lorsque des personnes publient des messages dans leurs salles de conversation.

</div>

<div>

## <a name="lync-web-app-updates"></a>Mises à jour de Lync Web App

Lync Web App est le client de conférence Web pour les réunions Lync Server 2013. Dans cette version, l’ajout de l’audio et de la vidéo à Lync Web App offre une expérience complète en réunion pour toute personne qui n’a pas de client Lync installé localement. Les participants à la réunion ont accès à toutes les fonctionnalités de collaboration et de partage et aux contrôles de réunion du présentateur.

Lorsqu’un utilisateur tente de rejoindre une réunion mais qu’il ne dispose pas d’un client installé en local, Lync Web App s’ouvre. Si vous souhaitez autoriser des options supplémentaires pour rejoindre la réunion, vous pouvez configurer la page de participation aux réunions ; consultez la rubrique [configuration de la page de participation aux réunions dans Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md) dans la documentation de déploiement.

En raison des améliorations apportées à Lync Web App, une version mise à jour de Attendee n’est pas disponible pour Lync Server 2013. Lync Web App est le client de choix pour les participants extérieurs à votre organisation. Aucun client local ne doit être installé, bien que les fonctionnalités audio, vidéo et de partage nécessitent l’installation d’un plug-in lors de la première utilisation.

</div>

<div>

## <a name="lync-2013-for-mobile-clients-updates"></a>Lync 2013 pour les mises à jour de clients mobiles

En plus des fonctionnalités avancées de présence, de contacts et de messagerie instantanée, les clients mobiles Lync 2013 fournissent désormais des appels vocaux et vidéo sur Internet et des connexions de données cellulaires. En un seul clic sur le lien de réunion dans un élément de calendrier, les utilisateurs mobiles peuvent rejoindre des réunions vocales et vidéo Lync. Pour plus d’informations sur les clients mobiles Lync 2013, voir [Planning for mobile clients in Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).

</div>

<div>

## <a name="lync-2013-user-interface-updates"></a>Mises à jour de l’interface utilisateur de Lync 2013

<div>

## <a name="accessibility-updates"></a>Mises à jour apportées à l’accessibilité

Lync 2013 intègre plusieurs nouvelles fonctionnalités d’accessibilité.

  - Lync 2013 prend en charge la résolution haute résolution, ce qui permet aux utilisateurs de mettre à l’échelle du texte et des graphiques pour 125% et 150% de points par pouce.

  - Lync offre une prise en charge à contraste élevé afin que l’interface utilisateur reste entièrement fonctionnelle lorsqu’elle est utilisée avec des thèmes à contraste élevé dans Windows.

  - Lync propose plus de 100 raccourcis clavier pour permettre aux utilisateurs d’accéder à des fonctions importantes sans souris. Par exemple, les utilisateurs peuvent appuyer sur Alt+C pour accepter un appel ou sur Alt+I pour l’ignorer, le tout sans changer d’onglet ou définir le focus. De plus, Alt+Q met fin à un appel, Ctrl+N démarre OneNote et Alt+T ouvre le menu Outils.

  - Une prise en charge étendue des lecteurs d’écran dans Lync 2013 garantit que toutes les notifications, les demandes entrantes et les messages instantanés sont lus à haute voix lorsqu’un lecteur d’écran est activé.

</div>

<div>

## <a name="presence-while-sharing"></a>Présence pendant le partage

Lorsque Lync détecte qu’un utilisateur partage, Lync lui attribue automatiquement un statut de présence. Cette situation bloque toutes les communications entrantes, sauf si l’expéditeur est affecté au niveau de confidentialité Groupe de travail. Si l’utilisateur utilise la fonctionnalité de partage entièrement sur un moniteur secondaire, Lync n’affecte pas un statut de présence de présentation.

</div>

<div>

## <a name="conversation-window-updates"></a>Mises à jour apportées à la fenêtre Conversation

Entièrement repensée, la fenêtre Conversation offre un accès rapide aux fonctions importantes.

  - Grâce à la nouvelle fonctionnalité de conversations par onglets, les utilisateurs peuvent à présent avoir l’ensemble de leurs messages instantanés et de leurs salles de conversation dans une seule fenêtre Conversation. Les onglets situés à gauche de la fenêtre Conversation permettent aux utilisateurs de naviguer facilement parmi toutes les conversations actives.

  - Les utilisateurs peuvent détacher une conversation individuelle dans une fenêtre séparée et redimensionner la fenêtre. Ils peuvent aussi faire revenir la fenêtre dans la fenêtre Conversation principale.

  - Lync 2013 ouvre à nouveau les conversations d’un utilisateur lorsque celui-ci se déconnecte, puis se reconnecte à Lync.

  - Les utilisateurs peuvent rapidement ajouter la messagerie instantanée, la vidéo, le partage de programme, le partage de Bureau ou des outils de conférence web (tableau blanc, notes de réunion, blocs-notes partagés et pièces jointes) à n’importe quelle conversation.

  - Lors d’une réunion dans laquelle la vidéo ou du contenu est partagé, les utilisateurs peuvent détacher la vidéo ou le contenu partagé de la réunion, puis redimensionner la fenêtre.

</div>

<div>

## <a name="lync-main-window-updates"></a>Mises à jour de la fenêtre principale Lync

La nouvelle apparence rationalisée conserve des fonctionnalités familières telles que le champ de note **Activités du jour**, le sélecteur de statut et le sélecteur **Définir votre emplacement**.

  - Lorsque les salles de conversation sont activées, les utilisateurs voient une nouvelle icône de salle de **conversation** sur la page principale de Lync. Avec l’icône **Salles de conversation**, les utilisateurs peuvent accéder rapidement à leurs salles de conversation et à leurs filtres.

  - Les utilisateurs peuvent cliquer sur les icônes de vue pour passer à la vue **Contacts**, **Salles de conversation**, **Conversations** ou **Téléphone**.

  - Si les utilisateurs ont été migrés vers Exchange 2013, ils peuvent télécharger une image haute résolution.

</div>

<div>

## <a name="contacts-view-and-contact-card-updates"></a>Mises à jour apportées à la vue Contacts et aux cartes de visite

Lync 2013 offre aux utilisateurs différentes façons d’afficher les contacts et les groupes dans leur affichage **contacts** .

  - Avec le nouveau magasin de contacts unifié, après la migration des contacts Lync des utilisateurs vers Exchange 2013, les utilisateurs peuvent accéder à leurs contacts et les gérer à partir de Lync 2013, Outlook ou Outlook Web App, et leurs favoris restent synchronisés. Par exemple, si un utilisateur ajoute un contact aux favoris dans Outlook, le contact apparaît dans le groupe favoris de Lync 2013.

  - Si vous avez ajouté et configuré le proxy XMPP et la passerelle XMPP, les utilisateurs peuvent ajouter des contacts de partenaires basés sur XMPP pour la messagerie instantanée et la présence.

  - La nouvelle fonctionnalité **Ajouter un contact qui ne fait pas partie de ma société** offre aux utilisateurs un moyen facile d’ajouter des personnes externes à l’organisation.

  - Le nouveau groupe **Favoris** permet aux utilisateurs de créer une liste de personnes qu’ils contactent le plus souvent pour un accès plus rapide.

  - Les utilisateurs peuvent utiliser la nouvelle page d’options **Liste de contacts** pour choisir la façon dont les utilisateurs souhaitent trier et afficher les contacts. Les utilisateurs peuvent sélectionner une vue développée sur deux lignes qui montre les images des contacts ou une vue condensée sur une ligne. Les utilisateurs peuvent également trier les contacts par ordre alphabétique ou par disponibilité.

</div>

<div>

## <a name="conferencing-updates"></a>Mises à jour apportées aux conférences

Lync 2013 offre plusieurs améliorations apportées aux fonctionnalités de conférence.

  - Selon le type de réunion, les utilisateurs peuvent à présent désactiver le micro de l’audience et autoriser ou bloquer le partage vidéo lors de la planification de la réunion. Ces options sont disponibles dans la page **Options de la réunion** et sont recommandées pour les grandes réunions de plus de 20 participants.

  - Des contrôles audio faciles à utiliser dans la salle de réunion permettent à l’utilisateur de contrôler les options audio, telles que l’activation du micro, la désactivation du micro, le changement de périphérique, etc.

  - Lors du partage de programmes, les utilisateurs peuvent sélectionner plusieurs programmes à partager s’ils ont besoin de travailler avec plus d’un programme.

  - Les utilisateurs peuvent à présent télécharger des présentations qui contiennent des clips vidéo en téléchargeant le fichier PowerPoint et en pointant la souris sur la diapositive pour afficher les contrôles vidéo (tels que Lire et Pause) et audio.

  - Au cours d’une réunion, les utilisateurs peuvent fusionner une autre conversation ouverte dans la réunion en sélectionnant **Fusionner cet appel dans** dans le menu **Autres options** (**...**).

  - Pour afficher le nom des participants, les utilisateurs peuvent pointer la souris sur le bouton **Afficher les participants** ou cliquer sur **Afficher la liste des participants** pour ancrer le volet à la réunion.

  - Selon le type de réunion, les utilisateurs ont le choix entre différentes vues du contenu et des participants.

  - Les enregistrements de réunion sont automatiquement enregistrés dans un format compatible avec le Lecteur Windows Media (MP4). Les utilisateurs peuvent facilement partager le fichier avec d’autres personnes ou utiliser la fonctionnalité **Publier** dans le Gestionnaire d’enregistrements pour publier l’enregistrement dans un emplacement partagé.

  - OneNote offre de nouvelles façons de collaborer dans une réunion. Au cours d’une réunion, les utilisateurs peuvent prendre des notes avec OneNote pour un usage personnel après la réunion, ou utiliser des blocs-notes partagés et les modifier en collaboration avec les participants en temps réel. Tous les membres de l’équipe peuvent accéder aux notes partagées pour contribuer aux informations, échanger des idées ou utiliser les pages du bloc-notes comme tableau blanc virtuel. Les personnes et le contenu partagés dans la réunion sont automatiquement ajoutés aux notes.

  - Les utilisateurs peuvent basculer entre les types de contenu à l’aide de l’option **Partager du contenu et mener des activités de réunion** en bas de la salle de réunion. Les utilisateurs peuvent également utiliser le menu **Gérer le contenu à présenter** pour choisir le contenu à partager.

</div>

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Planification des clients dans Lync Server 2013](lync-server-2013-planning-for-clients.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

