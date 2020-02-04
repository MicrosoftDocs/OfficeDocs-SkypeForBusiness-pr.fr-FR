---
title: 'Lync Server 2013 : Nouveautés pour les clients'
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
ms.openlocfilehash: f938ccc4e4a040307a7cf86a8084353c480cfdca
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758484"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="whats-new-for-clients-in-lync-server-2013"></a>Nouveautés pour les clients dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-19_

Microsoft Lync 2013 dispose d’une interface utilisateur repensée et de nouvelles fonctionnalités importantes. Pour les administrateurs, le client est désormais inclus dans le programme d’installation d’Office, offrant ainsi une approche plus rationalisée pour le déploiement d’Office et la personnalisation des clients au sein de votre organisation.

<div>


> [!NOTE]  
> Pour obtenir un affichage illustré des mises à jour de l’interface utilisateur de Lync 2013, voir « Nouveautés de Lync 2013 <A href="http://go.microsoft.com/fwlink/?linkid=273885">http://go.microsoft.com/fwlink/?LinkId=273885</A>».



</div>

<div>

## <a name="integration-with-office-setup"></a>Intégration à l’installation d’Office

Le client Lync 2013 et le complément réunion en ligne pour Lync 2013, qui prend en charge la gestion de la réunion à partir du client de messagerie et de collaboration Outlook, sont désormais inclus dans le programme d’installation d’Office 2013.

Dans les versions précédentes de Lync et Office Communicator, vous pouvez utiliser les propriétés Windows Installer pour personnaliser et contrôler l’installation d’Office. Dans la mesure où Lync 2013 est intégré au programme d’installation d’Office, vous pouvez utiliser les méthodes suivantes pour personnaliser le programme d’installation de Lync 2013 :

  - Utilisation de l’outil de personnalisation Office

  - Utiliser le fichier config. xml pour effectuer des tâches d’installation

  - Utiliser les options de la ligne de commande du programme d’installation

<div>


> [!NOTE]  
> Le programme d’installation de Lync 2013 ne désinstalle pas les versions précédentes de Lync ou d’Office Communicator. Le client Lync 2013 s’installe côte à côte avec d’autres clients Lync ou Office Communicator



</div>

Pour plus d’informations, reportez-vous à [déploiement de clients Lync dans Lync Server 2013](lync-server-2013-deploying-lync-clients.md).

</div>

<div>

## <a name="group-policy-deployment"></a>Déploiement d’une stratégie de groupe

Comme Lync 2013 est désormais inclus dans le programme d’installation d’Office, la méthode de déploiement des paramètres de stratégie de groupe Lync a changé. Dans les versions précédentes de Lync et d’Office Communicator, vous pouvez utiliser la fonction Communicator. adm pour définir les paramètres de stratégie de groupe, alors que dans Lync 2013, vous pouvez désormais utiliser les modèles d’administration ADMX et ADML fournis avec la stratégie de groupe Office Modèles d’administration.

Pour plus d’informations, voir [paramètres de stratégie de groupe pour Lync 2013](lync-server-2013-group-policy-settings-for-lync-2013.md).

</div>

<div>

## <a name="outlook-scheduling-add-in-updates"></a>Mises à jour de compléments de planification Outlook

Le complément réunion en ligne pour Lync 2013 inclut la personnalisation d’invitation à la réunion et les options de nouvelle réunion.

  - Les administrateurs peuvent personnaliser les invitations aux réunions de l’organisation en ajoutant un logo personnalisé, une URL d’assistance, une URL d’exclusion de responsabilité ou un texte de pied de page personnalisé. Pour plus d’informations, reportez-vous à [la rubrique Personnalisation du complément de réunion en ligne dans Lync Server 2013](lync-server-2013-customizing-the-online-meeting-add-in.md).

  - Les commandes de nouvelle option de désactivation des participants permettent aux organisateurs de la réunion de planifier des conférences qui ont désactivé le son et la vidéo des participants par défaut.

</div>

<div>

## <a name="virtual-desktop-infrastructure-plug-in"></a>Plug-in d’infrastructure de bureau virtuel

Le client Lync 2013 prend désormais en charge l’audio et la vidéo dans un environnement VDI (Virtual Desktop Infrastructure). Un utilisateur peut connecter un périphérique audio ou vidéo (par exemple, un casque ou un appareil photo) à l’ordinateur local (par exemple, un client léger ou un ordinateur réaffecté). L’utilisateur peut se connecter à la machine virtuelle, se connecter au client 2013 Lync qui s’exécute sur l’ordinateur virtuel et participer à une communication audio et vidéo en temps réel, comme si le client s’exécute localement. Les fonctionnalités suivantes sont prises en charge dans un environnement de bureau virtuel :

  - Intégration d’appareil pour l’audio et la vidéo, notamment les suivantes :
    
      - Contrôles d’appel à partir de l’appareil
    
      - Intégration de la présence sur l’appareil
    
      - Prise en charge de plusieurs HID (appareil d’interface utilisateur)

  - Emplacement et assistance technique pour les services d’urgence.

  - Prise en charge de toutes les modalités de Lync, notamment la messagerie instantanée, l’audio, la vidéo, le partage d’application, le partage de bureau, le partage PowerPoint, le tableau blanc et le transfert de fichiers.

  - Prise en charge de l’audio et de la vidéo dans les appels de personne à personne et aux conférences téléphoniques.

Pour plus d’informations sur le déploiement du plug-in VDI, voir [déploiement du plug-in LYNC VDI dans Lync Server 2013](lync-server-2013-deploying-the-lync-vdi-plug-in.md).

</div>

<div>

## <a name="video-enhancements"></a>Améliorations de la vidéo

Plusieurs nouvelles fonctions améliorent considérablement l’interface vidéo des participants à la Conférence.

  - La vidéo est améliorée grâce à la détection des visages et au cadre intelligent, de sorte que la vidéo d’un participant se déplace pour qu’elle reste centrée dans le cadre.

  - La vidéo haute définition est désormais prise en charge dans des appels à deux ou des conférences multiparties. Les utilisateurs peuvent bénéficier de résolutions jusqu’à HD 1080P.

  - Les participants peuvent faire votre choix parmi les différentes dispositions de la réunion : le mode Galerie affiche les images et les vidéos de tous les participants. Vue présentateur affiche le contenu de la réunion et uniquement la vidéo ou l’image du présentateur actuel. Le mode présentation affiche uniquement le contenu de la réunion. Affichage Compact affiche uniquement les contrôles de la réunion.

  - Grâce à la nouvelle fonctionnalité Galerie, les participants peuvent voir plusieurs flux vidéo en même temps. Si la Conférence compte plus de cinq participants, les flux vidéo des seuls participants les plus actifs apparaissent dans la ligne supérieure, et les images des autres participants.

  - Les participants peuvent utiliser le verrouillage vidéo pour sélectionner un ou plusieurs des flux vidéo disponibles à afficher à tout moment.

  - Les présentateurs peuvent utiliser la fonction actualités vidéo pour sélectionner le flux vidéo d’une personne de sorte que tous les participants à la réunion voient ce participant uniquement.

</div>

<div>

## <a name="chat-room-integration"></a>Intégration d’une salle de conversation

Lync 2013 intègre désormais les fonctionnalités précédemment fournies par la discussion de groupe Lync 2010. Un client de discussion de groupe distinct n’est plus nécessaire.

  - À partir de Lync 2013, les utilisateurs peuvent rechercher des salles de conversation, ajouter des salles de conversation à leurs contacts, surveiller l’activité des salles de conversation et lire et publier des messages.

  - Les utilisateurs peuvent créer des flux de sujets de sorte qu’ils soient avertis lorsqu’une personne figurant dans l’une de leurs salles de conversation ajoute un billet contenant des mots clés spécifiques.

  - La nouvelle page d’options de **conversation permanente** permet aux utilisateurs de définir des alertes et des sons de notification qui s’appliquent quand des personnes publient des messages dans leurs salles de conversation.

</div>

<div>

## <a name="lync-web-app-updates"></a>Mises à jour de Lync Web App

Lync Web App est le client de conférences Web pour les réunions Lync Server 2013. Dans cette version, l’ajout de l’audio et de la vidéo de l’ordinateur à Lync Web App fournit une interface complète en réunion aux personnes qui n’ont pas de client Lync installé en local. Les participants à une réunion ont accès à toutes les fonctionnalités de collaboration et de partage, tandis que le présentateur de la réunion dispose du contrôle.

Lorsqu’un utilisateur tente de participer à une réunion, mais qu’il n’a pas de client installé en local, Lync Web App s’ouvre. Si vous voulez autoriser d’autres options de participation à la réunion, vous pouvez configurer la page de participation à une réunion. Pour plus d’informations, reportez-vous à [la rubrique Configuration de la page de participation à une réunion dans Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md) .

En raison des améliorations apportées à Lync Web App, une version mise à jour du participant n’est pas disponible pour Lync Server 2013. Lync Web App est le client de votre choix pour les participants extérieurs à votre organisation. Aucune installation de client local n’est nécessaire, bien que les fonctionnalités audio, vidéo et de partage nécessitent qu’un plug-in soit installé lors de la première utilisation.

</div>

<div>

## <a name="lync-2013-for-mobile-clients-updates"></a>2013 Lync pour les clients mobiles mises à jour

Outre les fonctionnalités de présence, de contacts et de messagerie instantanée améliorées, les clients mobiles Lync 2013 permettent désormais des appels audio et vidéo via Internet et les connexions de données cellulaires. En un seul appui du lien de la réunion dans un élément de calendrier, les utilisateurs mobiles peuvent rejoindre des réunions audio et vidéo Lync. Pour plus d’informations sur les clients mobiles Lync 2013, voir [planification pour les clients mobiles dans Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).

</div>

<div>

## <a name="lync-2013-user-interface-updates"></a>Mises à jour de l’interface utilisateur de Lync 2013

<div>

## <a name="accessibility-updates"></a>Mises à jour de l’accessibilité

Lync 2013 inclut plusieurs nouvelles fonctionnalités d’accessibilité.

  - Lync 2013 prend en charge la résolution PPP élevée, permettant aux utilisateurs de mettre à l’échelle du texte et des graphismes pour 125% et 150% de points par pouce.

  - Lync fournit une prise en charge de contraste élevé afin que l’interface utilisateur reste entièrement fonctionnelle lorsqu’elle est utilisée avec des thèmes à contraste élevé dans Windows.

  - Lync propose plus de 100 raccourcis clavier pour permettre aux utilisateurs d’accéder à des fonctions importantes sans souris. Par exemple, les utilisateurs peuvent appuyer sur ALT + C pour accepter un appel, ou sur Alt + I pour l’ignorer sans avoir besoin d’appuyer sur la touche Tab ou de définir le focus. Appuyer sur (Alt + Q) met fin à un appel, (Ctrl + N) démarre OneNote et (Alt + T) ouvre le menu outils.

  - La prise en charge de lecteurs d’écran complets dans Lync 2013 permet de lire à haute voix toutes les notifications, demandes entrantes et messages instantanés lorsqu’un lecteur d’écran est activé.

</div>

<div>

## <a name="presence-while-sharing"></a>Présence lors du partage

Lorsque Lync détecte qu’un utilisateur partage, Lync attribue automatiquement à l’utilisateur un statut de présence de présentation. Ce statut bloque toutes les communications entrantes, sauf si l’expéditeur reçoit la relation de confidentialité groupe de travail. Si l’utilisateur utilise entièrement la fonctionnalité de partage sur un moniteur secondaire, Lync n’attribue pas de statut de présence présentant une présentation.

</div>

<div>

## <a name="conversation-window-updates"></a>Mises à jour de la fenêtre de conversation

La fenêtre de conversation repensée vous permet d’accéder plus rapidement aux fonctions importantes.

  - Grâce à la nouvelle fonctionnalité de conversations par onglets, les utilisateurs peuvent désormais conserver tous leurs messages instantanés et salles de conversation dans une seule fenêtre de conversation. Les onglets situés sur le côté gauche de la fenêtre de conversation permettent aux utilisateurs de naviguer facilement parmi toutes les conversations actives.

  - Les utilisateurs peuvent isoler une conversation individuelle dans une fenêtre séparée, puis redimensionner la fenêtre. Ils peuvent également intégrer la fenêtre dans la fenêtre de conversation principale.

  - Lync 2013 rouvert les conversations d’un utilisateur lorsque celui-ci se déconnecte et se reconnecte à Lync.

  - Les utilisateurs peuvent rapidement ajouter des messages instantanés, des vidéos, le partage de programmes, le partage de bureau ou des outils de conférence Web (tableau blanc, notes de réunion, blocs-notes partagés et pièces jointes) à une conversation.

  - Dans une réunion dans laquelle la vidéo ou le contenu est en cours de partage, les utilisateurs peuvent isoler la vidéo ou le contenu partagé de la réunion, puis redimensionner la fenêtre.

</div>

<div>

## <a name="lync-main-window-updates"></a>Mises à jour de la fenêtre principale de Lync

Le nouveau look rationalisé conserve les fonctionnalités familières telles que le champ **activités du jour** , le sélecteur d’État et la **configuration de votre** sélecteur d’emplacement.

  - Lorsque la messagerie instantanée est activée, les utilisateurs voient une nouvelle icône de **salles de conversation** dans la page principale de Lync. Les **salles de conversation** permettent aux utilisateurs d’accéder rapidement à leurs salles de conversation et filtres.

  - Les utilisateurs peuvent cliquer sur l’icône d’affichage pour basculer vers l’affichage **contacts** , la vue **salles de conversation** , l’affichage **conversations** ou le mode **téléphone** .

  - Si les utilisateurs ont été migrés vers Exchange 2013, ils peuvent télécharger une image de haute résolution.

</div>

<div>

## <a name="contacts-view-and-contact-card-updates"></a>Mises à jour de la carte de visite et du mode contacts

Lync 2013 offre aux utilisateurs différentes manières de afficher des contacts et des groupes dans leur affichage **contacts** .

  - Le nouveau magasin de contacts unifié, une fois que les contacts Lync des utilisateurs sont déplacés vers Exchange 2013, les utilisateurs peuvent accéder à leurs contacts et les gérer à partir de Lync 2013, Outlook ou Outlook Web App, et leurs favoris restent synchronisés. Par exemple, si un utilisateur ajoute un contact aux favoris dans Outlook, le contact apparaît dans le groupe favoris de Lync 2013.

  - Si vous avez ajouté et configuré le proxy XMPP et la passerelle XMPP, les utilisateurs peuvent ajouter des contacts de partenaires de XMPP pour la messagerie instantanée et la présence.

  - Un nouveau **contact ajouter un contact qui n’est pas présent dans ma société** offre aux utilisateurs un moyen facile d’ajouter des personnes externes à l’organisation.

  - Un nouveau groupe de **favoris** permet aux utilisateurs de créer une liste de personnes qui communiquent le plus souvent aux utilisateurs un accès plus rapide.

  - Les utilisateurs peuvent utiliser la nouvelle page d’options de la **liste de contacts** pour choisir la manière dont les utilisateurs veulent trier et afficher les contacts. Les utilisateurs peuvent sélectionner un affichage à deux lignes développé qui affiche les images des contacts ou un affichage d’une seule ligne condensé. Les utilisateurs peuvent également trier les contacts par ordre alphabétique ou par disponibilité.

</div>

<div>

## <a name="conferencing-updates"></a>Mises à jour de conférence

Lync 2013 offre plusieurs améliorations apportées aux fonctionnalités de conférence.

  - En fonction du type de réunion, les utilisateurs peuvent désormais désactiver le son du public et autoriser ou bloquer le partage vidéo lors de la planification de la réunion. Ces options sont disponibles sur la page Options de la **réunion** et sont recommandées pour les réunions de grande taille avec plus de 20 participants.

  - L’utilisation des contrôles audio simples dans la salle de réunion permet à l’utilisateur de contrôler les options audio, comme le silence, le réactivation du son, le changement de périphérique, etc.

  - Lorsque vous partagez des programmes, les utilisateurs peuvent sélectionner plusieurs programmes à partager s’ils ont besoin d’utiliser plusieurs programmes.

  - Les utilisateurs peuvent désormais télécharger des présentations qui contiennent des clips vidéo en téléchargeant le fichier PowerPoint et en pointant la souris sur la diapositive pour afficher des commandes vidéo (lecture, pause, contrôles audio, etc.).

  - Pendant la réunion, les utilisateurs peuvent fusionner une autre conversation ouverte dans la réunion en utilisant l’option **fusionner cet appel** dans le menu **autres options** (**...**).

  - Pour afficher les noms des participants, les utilisateurs peuvent survoler le pointeur de la souris au-dessus du bouton **voir les participants** ou cliquer sur Afficher la **liste des participants** pour ancrer le panneau dans la réunion.

  - En fonction du type de réunion, les utilisateurs peuvent sélectionner à partir de plusieurs affichages de contenus et de participants différents.

  - Les enregistrements de réunion sont automatiquement enregistrés dans un format lisible par le lecteur Windows Media (MP4). Les utilisateurs peuvent partager facilement le fichier avec tout le monde, ou utiliser la fonctionnalité de **publication** dans le gestionnaire d’enregistrements pour publier l’enregistrement à un emplacement partagé.

  - OneNote vous permet de créer de nouvelles façons de collaborer au cours d’une réunion. Au cours d’une réunion, les utilisateurs peuvent prendre des notes à l’aide de OneNote pour une utilisation personnelle après la réunion, ou utiliser des blocs-notes partagés et collaborer avec les participants à la réunion en temps réel. Tous les membres d’une équipe peuvent accéder aux notes partagées pour collaborer, rassembler des idées ou utiliser les pages de bloc-notes comme tableau blanc virtuel. Les personnes et le contenu partagés dans la réunion sont automatiquement ajoutés aux notes.

  - Les utilisateurs peuvent passer d’un type de contenu à un autre en utilisant **partager du contenu et mener des activités de réunion** en bas de la salle de réunion. Les utilisateurs peuvent également utiliser le menu **gérer le contenu à présenter** pour choisir le contenu qu’ils souhaitent partager.

</div>

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Planification pour les clients dans Lync Server 2013](lync-server-2013-planning-for-clients.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

