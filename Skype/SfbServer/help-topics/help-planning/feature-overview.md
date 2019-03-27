---
title: Feature Overview (Planning Tool)
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 4/6/2016
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.FeatureOverview
- ms.lync.plan.FeatureOverview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 44783b37-c87f-41f2-9de1-39176f1856ab
description: Outil de planification de Skype Entreprise Server 2015
ms.openlocfilehash: f04935f7dc4d27883e40b388051b9affa4ec30e9
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899735"
---
# <a name="feature-overview-planning-tool"></a>Feature Overview (Planning Tool)
 
Outil de planification de Skype Entreprise Server 2015
  
Vous pouvez utiliser la page **Sites centraux** de l’outil de planification pour concevoir le Skype pour le déploiement de serveur d’entreprise. Vous pouvez créer deux types de déploiement : centralisé ou distribué. Un déploiement centralisé n’a qu’un site central, qui héberge tous les Skype pour les utilisateurs professionnels de votre organisation. Un déploiement distribué comprend plusieurs sites centraux. Si vous déployez Skype pour Business Server sur plusieurs sites centraux, vous serez entrer le nombre d’utilisateurs sur chaque site central dans l’outil de planification.
  
Pour finaliser la définition du site central, vous devez tout d’abord fournir les informations suivantes :
  
- **Nom du site** Entrez le nom du Site central.
    
- **Nombre d’utilisateurs** Entrez le nombre d’utilisateurs, y compris les utilisateurs des sites de succursales qui sont hébergés sur le site central.
    
- **Nuage hébergés les utilisateurs** Entrez le nombre d’utilisateurs qui sont hébergés dans le site central à partir de Skype pour Business Online.
    
## <a name="ui-elements"></a>Éléments d’interface utilisateur

Les autres éléments ont été remplis avec les réponses fournies aux questions posées dans l’Assistant **Mise en route**, ou si vous avez annulé l’Assistant, sont automatiquement remplis par l’outil de planification.
  
### <a name="online-collaboration"></a>Collaboration en ligne

 La **collaboration en ligne** contient les options suivantes :
  
- **Messagerie instantanée et présence**
    
    La messagerie instantanée permet aux utilisateurs de communiquer en temps réel les uns avec les autres sur leurs ordinateurs à l’aide des messages textuels. Les sessions de messagerie unifiée à deux ou à plusieurs personnes sont prises en charge. La présence fournit aux utilisateurs des informations sur le statut de présence des autres utilisateurs sur le réseau. Statut de présence d’un utilisateur fournit des informations pour aider les autres à déterminer si l’utilisateur est en ligne et comment mieux contacter l’utilisateur. Par exemple, il est préférable de contacter un utilisateur qui est en réunion par e-mail.
    
- **Conférence audio et vidéo**
    
    La conférence audio et vidéo permet des conférences audio et vidéo en temps réel.
    
- **Conférence rendez-vous**
    
    La conférence rendez-vous permet aux utilisateurs de participer à une conférence audio/vidéo à partir d’un téléphone sur le réseau téléphonique commuté. La conférence rendez-vous nécessite le déploiement des applications Intendant Conférence et service d’annonce de conférence.
    
- **Conférence web**
    
    La conférence web permet aux utilisateurs professionnels situés à l’intérieur ou à l’extérieur du pare-feu de créer et de participer à des conférences en temps réel hébergées sur vos serveurs internes.
    
- **conversation permanente**
    
    La conversation permanent permet à plusieurs utilisateurs de participer à des conversations dans lesquelles ils publient et accèdent à du contenu sur certaines rubriques spécifiques, notamment du texte, des liens et des fichiers. Bien que les utilisateurs puissent communiquer en temps réel pendant une session, le contenu de chaque session est permanent, ce qui signifie qu’il reste disponible après la fin d’une session.
    
### <a name="users"></a>Utilisateurs

 Le champ **Utilisateurs** contient les options suivantes :
  
- **Organisation interne**
    
- **Fédération avec d’autres organisations**
    
- **Fédération avec les versions précédentes**
    
- **Fédération avec les fournisseurs de services de messagerie instantanée publics** Permet aux utilisateurs de votre organisation d’établir des communications avec des fournisseurs de services de messagerie instantanée publics tels que MSN, Yahoo! et AOL. Une licence séparée est requise pour établir la fédération avec les réseaux de messagerie instantanée publics.
    
- **Fédération avec les fournisseurs de services XMPP**
    
    Skype pour Business Server 2015 présente un proxy XMPP entièrement intégré (déployés sur les serveurs de périphérie) et une passerelle XMPP déployée sur vos serveurs frontaux. Vous pouvez déployer Ajout et la configuration du serveur proxy XMPP et la passerelle XMPP autorisera votre Skype pour les utilisateurs Business Server 2015 ajouter des contacts à partir de la présence et les partenaires basés sur XMPP pour la messagerie instantanée (IM).
    
- **Mobilité**
    
    Lorsque vous déployez le Skype pour le Service de mobilité 2015 Business Server, les utilisateurs peuvent utiliser pris en charge Apple iOS, Android, Windows Phone ou les appareils mobiles Nokia pour effectuer ces activités en tant que l’envoi et réception de messages instantanés, l’affichage des contacts et affichage de la présence.
    
- **Boîte aux lettres Exchange W15**
    
    Skype pour Business Server 2015 permet à votre messagerie vocale stockés dans Exchange messagerie unifiée (MU) ; Ces messages de messagerie vocale seront affiche alors en tant que messages électroniques dans la boîte de réception de vos utilisateurs.
    
### <a name="voice"></a>Audio

 **Audio** contient les options suivantes :
  
- **Voix Entreprise**
    
    Enterprise voice est la solution VoIP par logiciel de Microsoft. Voix entreprise permet aux utilisateurs d’utiliser Skype pour les entreprises pour passer un appel téléphonique à partir de leur ordinateur.
    
- **Messagerie unifiée Exchange**
    
    Messagerie unifiée Exchange (MU) combine la messagerie vocale et électronique en une seule infrastructure de messagerie. Skype pour Business Server 2015 utilise la messagerie unifiée Exchange pour fournir la réponse aux appels, l’accès abonné, notification d’appel et services de standard automatique. Si vous utilisez ces services, vous devrez intégrer la messagerie unifiée Exchange et Skype pour Business Server dans une topologie Active Directory partagée.
    
### <a name="additional-deployment-options"></a>Options de déploiement supplémentaires

 **Options de déploiement supplémentaires** contient les options suivantes :
  
- **Haute disponibilité**
    
    La haute disponibilité active les serveurs de secours pour la prise en charge du basculement.
    
- **Récupération d’urgence**
    
    Mesures de récupération d’urgence vous permettent de paire Front End pools situés dans deux centres de données.
    
- **Analyse**
    
    La surveillance capture des enregistrements détaillés liés aux sessions de communication. Elle collecte également des métriques des sessions audio et vidéo aux points de terminaison des participants. Le serveur de surveillance fournit les statistiques d’utilisation, les tendances et les statistiques de qualité des médias.
    
- **Archivage**
    
    L’archivage stocke les conversations et les conférences de messagerie instantanée.
    
- **Intégration de l’archivage Exchange**
    
    Si vous avez des utilisateurs qui sont hébergés sur Exchange 2013 et leurs boîtes aux lettres ont été placées en blocage sur Place, vous pouvez sélectionner l’option intégrer Skype pour le stockage des Business Server 2015 avec le stockage Exchange.
    
- **IPv4**
    
    Les adresses IPv4 sont des adresses 32 bits qui permettent aux ordinateurs de communiquer sur Internet. En raison du nombre croissant d’appareils dans le monde, il n’existe plus d’adresses IPv4 disponibles. C’est pourquoi, de nombreux nouveaux appareils utilisent désormais des adresses IPv6.
    
- **IPv6**
    
    Les adresses IPv6 ont le même rôle que les adresses IPv4 (avec des fonctionnalités supplémentaires), mais au lieu d’utiliser uniquement 32 bits, les adresses IPv6 utilisent 128 bits. Cela permet de nouvelles adresses, mais également un plus grand nombre d’adresses.
    
- **service web de mise à jour des périphériques**
    
    Le service Web de mise à jour des périphériques permet de mettre à jour tous les périphériques, tels que Skype pour Business pour Windows Phone, qui sont déployés à l’extérieur de votre organisation.
    
### <a name="server-applications"></a>Applications serveur

 **Applications serveur** contient les options suivantes :
  
- **Response Group**
    
    L’application Response Group répond automatiquement et distribue les appels vers un agent de support technique disponibles.
    
- **Annonce**
    
    Si vous prévoyez de déployer Enterprise Voice, vous souhaitez être en mesure de configurer la gestion des appels téléphoniques si le numéro composé est valide mais pas attribué à une zone commune utilisateur. Les administrateurs peuvent configurer le service d’annonce afin que ces appels soient transférés à une destination prédéterminée (numéro de téléphone ou URI SIP) ou qu’une annonce audio soit lue ou les deux. Le recours au service d’annonce évite toute situation inopportune, notamment quand un appelant compose un mauvais numéro et entend une tonalité de ligne occupée ou lorsque le client SIP reçoit un message d’erreur. La fonctionnalité de service d’annonce est une fonctionnalité PBX. 
    
- **parcage d’appel**
    
    Permet aux applications de parcage d’appel un utilisateur Enterprise Voice pour mettre un appel en attente à partir d’un téléphone, puis recevoir l’appel à partir d’un autre téléphone sans bloquer les ressources sur le téléphone qui a reçu l’appel. Application parcage d’appel est utile lorsqu’un utilisateur a besoin transférer un appel, mais le destinataire spécifique est inconnu. 
    
- **Intendant Conférence**
    
    Application intendant Conférence fournit les fonctionnalités de conférence audio pour les utilisateurs de téléphones sans le service d’un fournisseur de services d’audioconférence tiers.
    
- **Annonce de conférence**
    
    Annonce de conférence application génère des tonalités qui indiquent que les utilisateurs entrent ou quittent une conférence, ainsi que des notifications aux utilisateurs de téléphone lorsqu’ils sont activés ou désactivés.
    
- **Contrôle d’admission des appels**
    
    Le service Contrôle d’admission des appels (CAC), également appelé gestion de bande passante de réseau étendu (WAN), aide à éviter aux utilisateurs de vivre une expérience de qualité médiocre sur des réseaux encombrés en déterminant, sur la base de la bande passante réseau disponible, s’il faut autoriser l’établissement de sessions de communication en temps réel. 
    
    > [!NOTE]
    > Le CAC contrôle uniquement le trafic en temps réel sans que cela affecte le trafic de données. 
  
    Si une nouvelle session audio ou vidéo dépasse les limites de bande passante dont vous disposez sur un WAN, la session est bloquée ou (pour les appels téléphoniques uniquement) peut être réacheminée vers le PSTN.
    

