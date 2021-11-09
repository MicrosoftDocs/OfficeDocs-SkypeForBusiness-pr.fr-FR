---
title: Skype Entreprise Server Outil de planification de vue d’ensemble des fonctionnalités
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 4/6/2016
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.plan.FeatureOverview
- ms.lync.plan.FeatureOverview
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 44783b37-c87f-41f2-9de1-39176f1856ab
description: Informations sur l’outil Skype Entreprise Server de planification de vue d’ensemble des fonctionnalités.
ms.openlocfilehash: ac759dab4000ebdbe969b2d7436cbb46c408dc38
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60848877"
---
# <a name="skype-for-business-server-feature-overview-planning-tool"></a>Skype Entreprise Server Outil de planification de vue d’ensemble des fonctionnalités
 
outil de planification Skype Entreprise Server 2015
  
Vous pouvez utiliser la page **Sites centraux** de l’outil de planification pour concevoir le Skype Entreprise Server déploiement. Vous pouvez créer deux déploiements centralisés ou distribués. Un déploiement centralisé ne possède qu’un seul site central, qui Skype Entreprise tous les utilisateurs de votre organisation. Un déploiement distribué possède plusieurs sites centraux. Si vous déployez Skype Entreprise Server sur plusieurs sites centraux, vous entrez le nombre d’utilisateurs sur chaque site central dans l’outil de planification.
  
Pour terminer la définition du site central, vous devez d’abord fournir les informations suivantes :
  
- **Nom du site** Entrez le nom du site central.
    
- **Nombre d’utilisateurs** Entrez le nombre d’utilisateurs, y compris les utilisateurs des sites de succursale qui sont homed into the central site.
    
- **Utilisateurs d’accueil cloud** Entrez le nombre d’utilisateurs qui sont homed into the central site from Skype Entreprise Online.
    
## <a name="ui-elements"></a>Éléments d’interface utilisateur

Les autres éléments ont été remplis avec les réponses que vous avez fournies aux questions présentées dans l’Assistant **Prise en main** ou, si vous avez ignoré l’Assistant, automatiquement rempli par l’outil de planification.
  
### <a name="online-collaboration"></a>Collaboration en ligne

 **La collaboration en** ligne contient les options suivantes :
  
- **Messagerie instantanée et présence**
    
    La messagerie instantanée permet aux utilisateurs de communiquer les uns avec les autres en temps réel sur leurs ordinateurs à l’aide de messages texte. Les sessions de messagerie unifiée à deux ou à plusieurs personnes sont prises en charge. La présence fournit des informations aux utilisateurs sur l’état d’autres personnes sur le réseau. Le statut de présence d’un utilisateur fournit des informations pour aider d’autres personnes à déterminer si l’utilisateur est en ligne et comment contacter au mieux l’utilisateur. Par exemple, il est préférable de contacter un utilisateur qui se trouve dans une réunion par courrier électronique.
    
- **Conférence audio et vidéo**
    
    La conférence audio/vidéo (A/V) permet des conférences audio et vidéo en temps réel.
    
- **Conférence rendez-vous**
    
    La conférence rendez-vous permet aux utilisateurs de joindre un service A/V à partir d’un téléphone sur le réseau téléphonique téléphonique PSTN. La conférence dial-in nécessite que vous déployiez les applications Assistant de conférence et Annonce de conférence Service.
    
- **Conférence web**
    
    La conférence web permet aux utilisateurs d’entreprise à l’intérieur et à l’extérieur du pare-feu de créer et de participer à des conférences en temps réel hébergées sur vos serveurs internes.
    
- **Conversation permanente**
    
    La conversation permanente permet à plusieurs utilisateurs de participer à des conversations dans lesquelles ils publient et accèdent à du contenu sur des sujets spécifiques, notamment du texte, des liens et des fichiers. Bien que les utilisateurs puissent communiquer en temps réel pendant une session, le contenu de chaque session est permanent, ce qui signifie qu’il reste disponible après la fin d’une session.
    
### <a name="users"></a>Utilisateurs

 **Les utilisateurs** contiennent les options suivantes :
  
- **Organisation interne**
    
- **Fédération avec d’autres organisations**
    
- **Fédération avec les versions précédentes**
    
- **Fédération avec les fournisseurs de services de messagerie instantanée publics** Permet aux utilisateurs de votre organisation d’établir une communication avec des fournisseurs de services de messagerie instantanée publics tels que MSN, Yahoo! et AOL. Une licence distincte est nécessaire pour établir une fédération avec les réseaux de messagerie instantanée publics.
    
- **Fédération avec un fournisseur de services XMPP**
    
    Skype Entreprise Server 2015 introduit un proxy XMPP entièrement intégré (déployé sur les serveurs Edge) et une passerelle XMPP déployée sur vos serveurs frontaux. Vous pouvez déployer l’ajout et la configuration du proxy XMPP et de la passerelle XMPP pour permettre à vos utilisateurs Skype Entreprise Server 2015 d’ajouter des contacts de partenaires XMPP pour la messagerie instantanée et la présence.
    
- **Mobilité**
    
    Lorsque vous déployez le service de mobilité Skype Entreprise Server 2015, les utilisateurs peuvent utiliser les appareils mobiles Apple iOS, Android, Windows Phone ou Nokia pris en charge pour effectuer des activités telles que l’envoi et la réception de messages instantanés, l’affichage de contacts et l’affichage de la présence.
    
- **Boîte aux lettres Exchange W15**
    
    Skype Entreprise Server 2015 vous permet de stocker des messages vocaux dans Exchange messagerie unifiée ; Ces messages vocaux s’affichent ensuite sous la plupart des messages électroniques dans la boîte de réception de vos utilisateurs.
    
### <a name="voice"></a>Voix

 **Voice** contient les options suivantes :
  
- **Voix Entreprise**
    
    Enterprise voix est la solution VoIP de Microsft. Enterprise voix permet aux utilisateurs d’utiliser Skype Entreprise pour appeler leur ordinateur.
    
- **Messagerie unifiée Exchange**
    
    Exchange La messagerie unifiée combine la messagerie vocale et la messagerie électronique dans une infrastructure de messagerie unique. Skype Entreprise Server 2015 utilise la Exchange pour fournir des services de répondeur automatique, d’accès abonné, de notification d’appel et de service de transport automatique. Si vous utilisez ces services, vous devez intégrer la Exchange la Skype Entreprise Server dans une topologie Active Directory partagée.
    
### <a name="additional-deployment-options"></a>Options de déploiement supplémentaires

 **Les options de déploiement supplémentaires** contiennent les options suivantes :
  
- **Haute disponibilité**
    
    La haute disponibilité active les serveurs de veille pour la prise en charge duover.
    
- **Récupération d’urgence**
    
    Les mesures de récupération d’urgence vous permettent de jumeler des pools frontaux situés dans deux centres de données.
    
- **Analyse**
    
    La surveillance capture les enregistrements des détails des appels liés aux sessions de communication. Il collecte également des mesures à partir de sessions audio et vidéo aux points de terminaison des participants. Le serveur de surveillance fournit des statistiques d’utilisation, des tendances et des statistiques sur la qualité des médias.
    
- **Archivage**
    
    L’archivage stocke les conversations et les conférences de messagerie instantanée.
    
- **Exchange Intégration de l’archivage**
    
    Si des utilisateurs sont homed on Exchange 2013 et que leurs boîtes aux lettres ont été mises en conservation In-Place, vous pouvez sélectionner l’option d’intégration du stockage Skype Entreprise Server 2015 avec le stockage Exchange.
    
- **IPv4**
    
    Les adresses IPv4 sont des adresses 32 bits qui permettent à un ordinateur de communiquer sur Internet. En raison du nombre croissant d’appareils dans le monde, les adresses IPv4 disponibles sont à court. C’est pourquoi de nombreux nouveaux appareils utilisent des adresses IPv6.
    
- **IPv6**
    
    Les adresses IPv6 exécutent la même fonction que les adresses IPv4 (avec certaines fonctionnalités supplémentaires), mais au lieu d’utiliser uniquement des adresses 32 bits, les adresses IPv6 utilisent des adresses 128 bits. Cela fournit non seulement un nouvel ensemble d’adresses, mais également un plus grand nombre d’adresses.
    
- **service Web de mise à jour des périphériques**
    
    Le service Web de mise à jour des périphériques fournit un moyen automatisé de mettre à jour tous les appareils, tels que les Skype Entreprise pour Windows Phone, qui sont déployés en dehors de votre organisation.
    
### <a name="server-applications"></a>Applications serveur

 **Les applications serveur** contiennent les options suivantes :
  
- **Response Group**
    
    L’application Response Group répond et distribue automatiquement les appels à un agent de secours disponible.
    
- **Annonce**
    
    Si vous prévoyez de déployer Voix Entreprise, vous souhaiterez peut-être être en mesure de configurer la façon dont les appels téléphoniques sont gérés si le numéro composé est valide mais n’est pas affecté à une zone commune d’utilisateur. Les administrateurs peuvent configurer le service d’annonce afin que ces appels transfèrent vers une destination prédéterminée (numéro de téléphone ou URI SIP) ou lire une annonce audio ou les deux. L’utilisation du service d’annonce évite la situation dans laquelle un appelant maldialisation et entend une tonalité d’occupé ou le client SIP reçoit un message d’erreur. La fonctionnalité service d’annonce est une fonctionnalité PBX classique. 
    
- **Parcage d’appel**
    
    L’application de parcage d’appel permet à un utilisateur Voix Entreprise de mettre un appel en attente à partir d’un téléphone, puis de recevoir l’appel d’un autre téléphone sans lier les ressources sur le téléphone qui a reçu l’appel. L’application de parcage d’appel est utile lorsqu’un utilisateur doit transférer un appel, mais que le destinataire spécifique est inconnu. 
    
- **Conference Attendant**
    
    application Assistant de conférence offre des fonctionnalités d’audioconférence aux utilisateurs téléphoniques sans le service d’un fournisseur de services d’audioconférence tiers.
    
- **Annonce de conférence**
    
    application Annonce de conférence produit des tonalités signalant que les utilisateurs entrent ou quittent une conférence, ainsi que des notifications aux utilisateurs de téléphone lorsqu’ils sont en mode silencieux ou non.
    
- **Contrôle d’admission des appels**
    
    Le contrôle d’admission des appels (CAC), également appelé gestion de la bande passante wan, permet d’éviter une mauvaise qualité d’expérience pour les utilisateurs sur des réseaux saturés en déterminant, en fonction de la bande passante disponible, s’il faut autoriser et établir de nouvelles sessions de communication en temps réel. 
    
    > [!NOTE]
    > Le contrôle d’accès au contrôle d’accès contrôle uniquement le trafic en temps réel et n’affecte pas le trafic de données. 
  
    Si une nouvelle session vocale ou vidéo dépasse les limites de bande passante que vous avez allouées sur un réseau wan, la session est bloquée ou (pour les appels téléphoniques uniquement) réacheminée vers le réseau téléphonique (PSTN).
    

