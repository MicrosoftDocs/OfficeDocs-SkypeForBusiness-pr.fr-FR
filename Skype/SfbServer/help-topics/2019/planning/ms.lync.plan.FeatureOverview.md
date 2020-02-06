---
title: Feature Overview (Planning Tool)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.plan.FeatureOverview
- ms.lync.plan.FeatureOverview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 44783b37-c87f-41f2-9de1-39176f1856ab
ROBOTS: NOINDEX, NOFOLLOW
description: Outil de planification de Skype entreprise Server
ms.openlocfilehash: 35fd0d44bbfde381b18eaf7c4e009b623dea8888
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41797195"
---
# <a name="feature-overview-planning-tool"></a>Feature Overview (Planning Tool)
 
Outil de planification de Skype entreprise Server
  
Vous pouvez utiliser la page **sites centraux** de l’outil planification pour concevoir le déploiement de Skype entreprise Server. Vous pouvez créer deux types de déploiement : centralisé ou distribué. Un déploiement centralisé dispose d’un seul site central, qui est l’un des utilisateurs Skype entreprise de votre organisation. Un déploiement distribué comprend plusieurs sites centraux. Si vous déployez Skype entreprise Server sur plusieurs sites centraux, vous devez entrer le nombre d’utilisateurs dans chaque site central de l’outil de planification.
  
Pour finaliser la définition du site central, vous devez tout d’abord fournir les informations suivantes :
  
- **Nom du site** Entrez le nom du Site central.
    
- **Nombre d’utilisateurs** Entrez le nombre d’utilisateurs, y compris les utilisateurs des sites de succursales qui sont hébergés sur le site central.
    
- **Utilisateurs à domicile** dans le Cloud Entrez le nombre d’utilisateurs hébergés sur le site central à partir de Skype entreprise online.
    
## <a name="ui-elements"></a>Éléments d’interface utilisateur

Les autres éléments ont été remplis avec les réponses fournies aux questions posées dans l’Assistant **Mise en route**, ou si vous avez annulé l’Assistant, sont automatiquement remplis par l’outil de planification.
  
### <a name="online-collaboration"></a>Collaboration en ligne

 La **collaboration en ligne** contient les options suivantes :
  
- **Messagerie instantanée et présence**
    
    La messagerie instantanée permet aux utilisateurs de communiquer en temps réel les uns avec les autres sur leurs ordinateurs à l’aide des messages textuels. Les sessions de messagerie unifiée à deux ou à plusieurs personnes sont prises en charge. La présence fournit aux utilisateurs des informations sur le statut de présence des autres utilisateurs sur le réseau. Le statut de présence d’un utilisateur fournit des informations pour aider les autres à déterminer si l’utilisateur est en ligne et comment contacter au mieux l’utilisateur. Par exemple, il est préférable de contacter un utilisateur qui est en réunion par e-mail.
    
- **Conférence audio et vidéo**
    
    La conférence audio et vidéo permet des conférences audio et vidéo en temps réel.
    
- **Conférence rendez-vous**
    
    La conférence rendez-vous permet aux utilisateurs de participer à une conférence audio/vidéo à partir d’un téléphone sur le réseau téléphonique commuté. La conférence rendez-vous nécessite le déploiement des applications Intendant Conférence et service d’annonce de conférence.
    
- **Conférence web**
    
    La conférence web permet aux utilisateurs professionnels situés à l’intérieur ou à l’extérieur du pare-feu de créer et de participer à des conférences en temps réel hébergées sur vos serveurs internes.
    
- **conversation permanente**
    
    La conversation permanent permet à plusieurs utilisateurs de participer à des conversations dans lesquelles ils publient et accèdent à du contenu sur certaines rubriques spécifiques, notamment du texte, des liens et des fichiers. Bien que les utilisateurs puissent communiquer en temps réel pendant une session, le contenu de chaque session est permanent, ce qui signifie qu’il reste disponible après la fin d’une session.

    > [!NOTE] 
    > La conversation permanente est disponible dans Skype entreprise Server 2015, mais n’est plus prise en charge dans Skype entreprise Server 2019. La même fonctionnalité est disponible dans Microsoft Teams. Pour plus d’informations, reportez-vous à la rubrique [mise à niveau de Skype entreprise vers Microsoft teams](https://docs.microsoft.com/MicrosoftTeams/upgrade-start-here). Si vous avez besoin d’utiliser une conversation permanente, vous pouvez migrer les utilisateurs qui ont besoin de cette fonctionnalité pour teams ou continuer à utiliser Skype entreprise Server 2015.
    
### <a name="users"></a>Utilisateurs

 Le champ **Utilisateurs** contient les options suivantes :
  
- **Organisation interne**
    
- **Fédération avec d’autres organisations**
    
- **Fédération avec les versions précédentes**
    
- **Fédération avec les fournisseurs de services de messagerie instantanée publics** Permet aux utilisateurs de votre organisation d’établir des communications avec des fournisseurs de services de messagerie instantanée publics tels que MSN, Yahoo! et AOL. Une licence séparée est requise pour établir la fédération avec les réseaux de messagerie instantanée publics.
    
- **Fédération avec les fournisseurs de services XMPP**
    
    Skype entreprise Server 2015 a introduit un proxy XMPP entièrement intégré (déployé sur les serveurs Edge) et une passerelle XMPP déployée sur votre serveur frontal. Vous pouvez déployer l’ajout et la configuration du proxy XMPP et de la passerelle XMPP, qui permettra à vos utilisateurs de Skype entreprise Server d’ajouter des contacts des partenaires de XMPP pour la messagerie instantanée et la présence.
    
- **Mobilité**
    
    Lorsque vous déployez le service de mobilité Skype entreprise Server, les utilisateurs peuvent utiliser les appareils mobiles Apple iOS, Android, Windows Phone ou Nokia pour effectuer des opérations telles que l’envoi et la réception de messages instantanés, l’affichage de contacts et l’affichage de la présence.
    
- **Boîte aux lettres Exchange W15**
    
    Skype entreprise Server vous permet de disposer de messages vocaux stockés dans la messagerie unifiée Exchange (MU); ces messages vocaux apparaissent alors sous forme de courriers dans les boîtes de réception de vos utilisateurs.

    > [!NOTE]
    > La messagerie unifiée Exchange telle qu’auparavant connue n’est plus disponible dans Exchange 2019, mais vous pouvez toujours utiliser le système téléphonique pour enregistrer les messages vocaux, puis conserver l’enregistrement dans la boîte aux lettres Exchange d’un utilisateur. Pour plus d’informations, voir [planifier le service de messagerie vocale Cloud](../../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) .
    
### <a name="voice"></a>Audio

 **Audio** contient les options suivantes :
  
- **Voix Entreprise**
    
    Enterprise Voice est une solution VoIP basée sur le logiciel. Voix entreprise permet aux utilisateurs d’utiliser Skype entreprise pour passer un appel à partir de leur ordinateur.
    
- **Messagerie unifiée Exchange**
    
    La messagerie unifiée Exchange combine la messagerie vocale et le courrier électronique en une seule infrastructure de messagerie. Skype entreprise Server 2015 utilise la messagerie unifiée Exchange pour fournir des réponses aux appels, des accès abonnés, des notifications d’appel et des services de standard automatique. Si vous utilisez ces services, vous devez intégrer Exchange UM et Skype entreprise Server dans une topologie Active Directory partagée.

    > [!NOTE]
    > La messagerie unifiée Exchange telle qu’auparavant connue n’est plus disponible dans Exchange 2019, mais vous pouvez toujours utiliser le système téléphonique pour enregistrer les messages vocaux, puis conserver l’enregistrement dans la boîte aux lettres Exchange d’un utilisateur. Pour plus d’informations, voir [planifier le service de messagerie vocale Cloud](../../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) .
    
### <a name="additional-deployment-options"></a>Options de déploiement supplémentaires

 **Options de déploiement supplémentaires** contient les options suivantes :
  
- **Haute disponibilité**
    
    La haute disponibilité active les serveurs de secours pour la prise en charge du basculement.
    
- **Récupération d’urgence**
    
    Les mesures de reprise après sinistre vous permettent de jumeler les pools front-end situés dans deux centres de données.
    
- **Analyse**
    
    La surveillance capture des enregistrements détaillés liés aux sessions de communication. Elle collecte également des métriques des sessions audio et vidéo aux points de terminaison des participants. La surveillance du serveur fournit des statistiques d’utilisation, des tendances et des statistiques de qualité multimédia.
    
- **Archivage**
    
    L’archivage stocke les conversations et les conférences de messagerie instantanée.
    
- **Intégration de l’archivage Exchange**
    
    Si vous avez des utilisateurs hébergés sur Exchange et que leurs boîtes aux lettres ont été placées sur place, vous pouvez sélectionner l’option d’intégration du stockage de Skype entreprise Server au stockage Exchange.
    
- **IPv4**
    
    Les adresses IPv4 sont des adresses 32 bits qui permettent aux ordinateurs de communiquer sur Internet. En raison du nombre croissant d’appareils dans le monde, il n’existe plus d’adresses IPv4 disponibles. C’est pourquoi, de nombreux nouveaux appareils utilisent désormais des adresses IPv6.
    
- **IPv6**
    
    Les adresses IPv6 ont le même rôle que les adresses IPv4 (avec des fonctionnalités supplémentaires), mais au lieu d’utiliser uniquement 32 bits, les adresses IPv6 utilisent 128 bits. Cela permet de nouvelles adresses, mais également un plus grand nombre d’adresses.
    
- **service web de mise à jour des périphériques**
    
    Le service Web de mise à jour des appareils fournit un moyen automatisé de mettre à jour tous les appareils, tels que Skype entreprise pour Windows Phone, déployés en dehors de votre organisation.
    
### <a name="server-applications"></a>Applications serveur

 **Applications serveur** contient les options suivantes :
  
- **Response Group**
    
    L’application Response Group répond automatiquement et distribue les appels à un agent de support technique disponible.
    
- **Annonce**
    
    Si vous envisagez de déployer Enterprise Voice, vous souhaiterez peut-être configurer la gestion des appels téléphoniques Si le numéro composé est valide, mais n’est pas attribué à une zone commune de l’utilisateur. Les administrateurs peuvent configurer le service d’annonce afin que ces appels soient transférés à une destination prédéterminée (numéro de téléphone ou URI SIP) ou qu’une annonce audio soit lue ou les deux. Le recours au service d’annonce évite toute situation inopportune, notamment quand un appelant compose un mauvais numéro et entend une tonalité de ligne occupée ou lorsque le client SIP reçoit un message d’erreur. La fonctionnalité de service d’annonce est une fonctionnalité PBX. 
    
- **parcage d’appel**
    
    L’application de stationnement d’appel permet à un utilisateur de voix entreprise de mettre un appel en attente à partir d’un téléphone, puis de réceptionner l’appel d’un autre téléphone sans mettre en place des ressources sur le téléphone ayant reçu l’appel. L’application de parc d’appels est utile lorsqu’un utilisateur doit transférer un appel, mais qu’il n’est pas connu. 
    
- **Intendant Conférence**
    
    L’application de surveillance des conférences fournit des fonctionnalités d’audioconférence aux utilisateurs de téléphone sans le service d’un fournisseur de services d’audioconférence tiers.
    
- **Annonce de conférence**
    
    L’application annonce d’annonce génère des tonalités indiquant que les utilisateurs entrent ou quittent une conférence, ainsi que des notifications aux utilisateurs du téléphone quand ils sont en sourdine ou en mode muet.
    
- **Contrôle d’admission des appels**
    
    Le service Contrôle d’admission des appels (CAC), également appelé gestion de bande passante de réseau étendu (WAN), aide à éviter aux utilisateurs de vivre une expérience de qualité médiocre sur des réseaux encombrés en déterminant, sur la base de la bande passante réseau disponible, s’il faut autoriser l’établissement de sessions de communication en temps réel. 
    
    > [!NOTE]
    > Le CAC contrôle uniquement le trafic en temps réel sans que cela affecte le trafic de données. 
  
    Si une nouvelle session audio ou vidéo dépasse les limites de bande passante dont vous disposez sur un WAN, la session est bloquée ou (pour les appels téléphoniques uniquement) peut être réacheminée vers le PSTN.
    

