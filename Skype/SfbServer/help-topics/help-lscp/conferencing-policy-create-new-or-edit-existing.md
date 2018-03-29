---
title: Stratégie de conférence créer ou modifier une existante
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ConfMeetingPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ebd2f120-b57a-4c94-9509-20e098f4b0f4
description: Une stratégie de conférence définit les fonctionnalités et les fonctions à la disposition des utilisateurs lors d’une conférence (également appelée « réunion »).
ms.openlocfilehash: 7840eb2d30c40440d82d0cdc6d2bcf38ac894c4b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="conferencing-policy-create-new-or-edit-existing"></a>Stratégie de conférence : création d’une stratégie ou modification d’une création existante
 
Une stratégie de conférence définit les fonctionnalités et les fonctions à la disposition des utilisateurs lors d’une conférence (également appelée « réunion »).
  
## <a name="ui-reference"></a>Référence d’interface utilisateur

La liste ci-dessous décrit les champs de la page.
  
- **Champ d’application** Identifie l’étendue de la stratégie de conférence que vous créez ou modifiez : global, site ou à l’utilisateur.
    
- **Nom** Chaque stratégie de conférence requiert un nom. Stratégies de conférence globaux et de site sont nommées par défaut, et le nom ne peut pas être modifié. Stratégies d’utilisateurs conférence, utilisez un nom descriptif qui identifie l’utilisateur ou le groupe d’utilisateurs.
    
    > [!NOTE]
    > Une fois que vous avez enregistré la stratégie de conférence, son nom ne peut plus être modifié. 
  
- **Description** Ce champ est facultatif. Elle permet de fournir des détails supplémentaires sur la politique de la conférence.
    
- **Stratégie de la bibliothèque multimédia** Les paramètres de cette section s’appliquent à l’utilisateur qui organise une conférence. Si un paramètre est sélectionné, l’utilisateur peut organiser une conférence qui a les caractéristiques spécifiées. Si un paramètre n’est pas sélectionné, l’utilisateur ne peut pas organiser une conférence avec cette caractéristique. Ces paramètres ne déterminent pas à ce que l’utilisateur a accès à en tant que participant dans les conférences.
    
    Cliquez sur la flèche vers le haut ou la flèche vers le bas en regard de l’étiquette pour fermer ou ouvrir la section.
    
- **Taille de la réunion d’au maximum** le nombre maximal d’utilisateurs qui sont autorisés à une conférence. Par défaut, la taille maximale de la réunion est de 250.
    
- **Autoriser les participants à inviter des utilisateurs anonymes** Activez cette case à cocher pour permettre aux utilisateurs d’inviter des utilisateurs anonymes aux conférences. Les utilisateurs anonymes sont des utilisateurs qui n’ont pas d’informations d’identification des Services de votre organisation de domaine Active Directory et qui, par conséquent, ne sont pas authentifiés.
    
- **Enregistrement** Permet de spécifier si les participants peuvent enregistrer des conférences. Les options sont **Aucun** , ou **Activer l’enregistrement**.
    
- **Autoriser fédéré et anonymes participants à enregistrer** Activez cette case à cocher pour autoriser les participants externes et non authentifiés aux conférences de l’enregistrement.
    
- **Audio/vidéo** Spécifier si les participants peuvent utiliser audio et vidéo :
    
  - **Aucun** Sélectionnez cette option pour empêcher l’utilisation de l’audio et la vidéo.
    
  - **Enable IP audio** Sélectionnez cette option pour autoriser l’utilisation de l’audio mais pas de vidéo.
    
  - **Enable IP audio/vidéo** Sélectionnez cette option pour permettre à la fois audio et vidéo.
    
- **Activer le RTPC-in conférence** Si vous avez activé l’audio dans **Audio/vidéo**, cette case à cocher pour autoriser les utilisateurs à se connecter à des conférences à l’aide du réseau téléphonique public commuté (RTPC).
    
- **Autoriser les participants pour établir une connexion anonymes** Activez cette case à cocher si vous autorisez les utilisateurs à se connecter à des conférences et que vous souhaitez autoriser des utilisateurs (anonymes) non authentifiés à participer à une conférence à l’aide d’appels sortants de diffuser. Avec cette fonctionnalité, le serveur de conférence appelle l’utilisateur et celui-ci répond au téléphone pour participer à la conférence.
    
- **Autoriser les participants à ne pas activés pour les Voix Entreprise pour les appels sortants** Si vous avez activé l’audio dans **Audio/vidéo**, cette case à cocher pour permettre aux utilisateurs qui ne sont pas activés pour les Voix Entreprise participer à une conférence à l’aide de diffuser des appels sortants. Avec les appels sortants diffuser la conférence serveur téléphones de l’utilisateur, puis l’utilisateur répond au téléphone pour participer à la conférence.
    
- **Autoriser plusieurs flux vidéo** Si vous avez activé la vidéo dans **cette vidéo**, cette case à cocher pour permettre aux utilisateurs d’organiser des conférences vidéo de la galerie photos. Lorsque cette case à cocher est activée, ce paramètre permet aux utilisateurs d’organiser des conférences d’envoyer plusieurs flux vidéo. Lorsque cette case à cocher n’est pas sélectionnée, les utilisateurs peuvent organiser uniquement les conférences qui envoient un seul flux vidéo.
    
    > [!NOTE]
    > Cette option détermine le type de flux vidéo pris en charge par la conférence. Il ne détermine pas si les participants peuvent recevoir plusieurs flux vidéo. L’option **Autoriser les participants à rejoindre plusieurs flux de données vidéo** détermine si les participants peuvent recevoir plusieurs flux vidéo.
  
- **Collaboration de données** Permet de spécifier si Oui ou non la conférence permet de collaboration de données. Les options sont **Aucun** , ou **Activer la collaboration de données**.
    
    Les paramètres ci-dessous concernent la collaboration de données :
    
  - **Autoriser fédéré et anonymes participants de télécharger du contenu** Si vous autorisez la collaboration de données, activez cette case à cocher pour permettre à des utilisateurs non authentifiés et externes télécharger du contenu, tels que des diapositives ou des documents, à partir d’une conférence.
    
  - **Autoriser les participants à transférer des fichiers** Si vous autorisez la collaboration de données, activez cette case à cocher pour autoriser les transferts de fichiers à tous les participants au cours d’une conférence.
    
  - **Activer les annotations** Si vous autorisez la collaboration de données, cette case à cocher pour permettre aux participants d’apporter à l’écran les annotations sur le contenu partagé au cours de la conférence.
    
  - **Annotations permettent de PowerPoint** Si vous autorisez l’annotation, cette case à cocher pour autoriser les participants à apporter des annotations de diapositives PowerPoint partagés au cours de la conférence.
    
  - **Activer les sondages** Si vous autorisez la collaboration de données, activez cette case à cocher pour autoriser les participants à conserver un sondage au cours d’une conférence.
    
- **Partage d’application** Permet de spécifier si Oui ou non la conférence permet le partage d’application. Les options sont **désactiver le partage d’application** ou **Activer le partage d’application**.
    
    Les paramètres ci-dessous concernent le partage d’application :
    
  - **Autoriser les participants à prendre le contrôle** Si vous autorisez le partage d’applications, cette case à cocher pour autoriser les participants à prendre le contrôle des applications ou des postes de travail qui sont partagés au cours de la conférence.
    
  - **Autoriser fédéré et anonymes participants de prendre le contrôle** Si vous autorisez le partage d’applications, cette case à cocher pour autoriser les participants externes et non authentifiés de prendre le contrôle des applications ou des postes de travail qui sont partagés au cours de la conférence.
    
- **Stratégie de participant** Les paramètres de cette section s’appliquent aux utilisateurs en tant que participants dans une conférence ou une session de deux tiers. Étant donné que les paramètres suivants sont les paramètres par utilisateur, un seul utilisateur dans une conférence ou une session de deux tiers peut avoir des capacités différentes de celles d’un autre utilisateur dans la même conférence ou une session de deux tiers.
    
    Cliquez sur la flèche vers le haut ou la flèche vers le bas en regard de l’étiquette pour fermer ou ouvrir la section.
    
- Sélectionnez **Activer le partage d’application et de Bureau** pour autoriser les utilisateurs à partager les applications et leur Bureau lorsqu’ils participent à une conférence ou à une session à deux participants. Sélectionnez **Désactiver le partage d’application et de Bureau** pour empêcher les utilisateurs de partager les applications et leur Bureau lorsqu’ils participent à une conférence ou à une session à deux participants.
    
- **Activer le transfert de fichiers d’homologue à homologue** Activez cette case à cocher pour autoriser les transferts de fichiers de personne à personne (autrement dit, les transferts de fichier qui n’impliquent pas de tous les participants) au cours d’une conférence ou une session de deux tiers.
    
- **Activer l’enregistrement d’homologue à homologue** Activez cette case à cocher pour permettre aux utilisateurs d’enregistrer des sessions de deux tiers.
    
- **Permettre aux participants de joindre plusieurs flux vidéo** Activez cette case à cocher pour autoriser les participants à recevoir les signaux vidéo de la galerie dans les conférences qui lui. Si cette option n’est pas sélectionnée, les participants peuvent uniquement recevoir un flux vidéo unique, quel que soit ce qui permet à la conférence.
    
    > [!NOTE]
    > L’option **Autoriser plusieurs flux de données vidéo** détermine si une conférence autorise plusieurs flux vidéo.
  
Pour plus d’informations sur les fonctionnalités de conférence de, consultez [Vue d’ensemble de la conférence](http://technet.microsoft.com/library/5bb90e69-3d4f-4d59-a1ee-2550de84439f.aspx) dans la documentation de planification. Pour plus d’informations sur l’utilisation des stratégies de la conférence, voir [Stratégies de conférence](http://technet.microsoft.com/library/8f92eb7c-ee66-4df6-a726-4bff93b122cb.aspx) dans la documentation sur les opérations.
  

