---
title: Configuration de la réunion, créer ou modifier une existante
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ConfMeetingSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8fc19fa-6cd7-4f68-b90a-1c7e1b649abd
description: Les paramètres de configuration de réunion définissent la participation des utilisateurs pour les conférences planifiées par des utilisateurs. Ces paramètres ne concernent que les réunions planifiées. Elles ne s’appliquent pas à des réunions ad hoc créées en cliquant sur l’option Conférence maintenant dans le client.
ms.openlocfilehash: af9a1cca6a34320a7e2bd2ba53b08040351f784e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="meeting-configuration-create-new-or-edit-existing"></a>Configuration de la réunion : création d’une réunion ou modification d’une réunion existante
 
Les paramètres de configuration de réunion définissent la participation des utilisateurs pour les conférences planifiées par des utilisateurs. Ces paramètres ne concernent que les réunions planifiées. Ils ne concernent pas les réunions ad hoc créées en cliquant sur l’option **Conférence maintenant** du client.
  
## <a name="ui-reference"></a>Référence d’interface utilisateur

La liste ci-dessous décrit les champs de la page.
  
- **Champ d’application** Identifie la portée de la configuration de la réunion que vous créez ou modifiez : global, site, ou le pool.
    
- **Nom** Configurations de réunion sont nommées par défaut, et le nom ne peut pas être modifié.
    
- **Les appelants RTPC contournent la salle d’attente** Activez cette case à cocher d’admettre automatiquement les utilisateurs qui sont connectent à la conférence via une ligne téléphonique du réseau téléphonique public commuté. Désactivez cette case à cocher aux appelants de RTPC d’itinéraire à la salle de conférence, où qu’ils se trouvent sur Maintenez jusqu'à ce qu’un présentateur de la conférence leur accorde l’accès à la conférence.
    
- **Désigner en tant que présentateur** Sélectionnez la catégorie d’utilisateurs sont automatiquement désigné en tant que présentateurs lorsqu’ils rejoignent une conférence (en plus de l’organisateur de la réunion). Indépendamment de ce paramètre, les présentateurs peuvent être explicitement désignés en tant que présentateurs lors de la conférence est planifiée, ou ils peuvent être promus explicitement au présentateur au cours de la conférence. Les options sont les suivantes :
    
  - **Aucun** Sélectionnez cette option si la personne que l’organisateur est automatiquement désigné en tant que présentateur.
    
  - **Société** Sélectionnez cette option pour désigner automatiquement uniquement les membres de votre organisation en tant que présentateurs.
    
  - **Tout le monde** Sélectionnez cette option pour désigner automatiquement tous les utilisateurs d’être un présentateur.
    
- **Type de conférence attribué par défaut** Ce paramètre contrôle si le complément de conférence Outlook planifie toujours les conférences à l’aide de l’organisateur affecté de conférence, qui signifie que prévu des conférences toujours ont la même URL de jointure et les informations audio. Activez cette case à cocher pour que les conférences planifiées à toujours utiliser la même URL de jointure. Désactivez cette case à cocher pour utiliser une URL de jointure différente pour chaque conférence.
    
- **Admit les utilisateurs anonymes par défaut** Activez cette case à cocher si anonyme (c'est-à-dire, non authentifié) les utilisateurs sont autorisés à participer à des conférences par défaut. Désactivez cette case à cocher si les utilisateurs anonymes ne sont pas autorisés à participer à des conférences par défaut.
    
- **URL du logo** Tapez l’URL contenant l’image à utiliser pour les invitations Conférence personnalisé.
    
- **URL d’aide** Tapez l’URL d’un site Web où les utilisateurs peuvent obtenir une assistance pour joindre la conférence.
    
- **URL de texte juridique** Tapez l’URL d’un site Web qui a les informations légales et limitation de responsabilité pour la conférence.
    
- **Texte de pied de page personnalisé** Tapez le texte à utiliser sur les invitations Conférence personnalisé.
    
Pour plus d’informations sur l’utilisation des configurations de réunion, reportez-vous à la section [créer un ou modifier une Collection de réunion Configuration paramètres](http://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) dans la documentation sur les opérations. Pour plus d’informations sur la définition de configurations de réunion pour les réunions de grande taille, consultez [Configuration de Support pour les réunions de grande taille](http://technet.microsoft.com/library/8e22d34b-b395-408d-9d48-8f2a3abe9513.aspx) dans la documentation de planification.
  

