---
title: Configurer la connectivité hybride | Déployer Skype entreprise Server 2019 Connect
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Instructions pour la mise en œuvre d’une connectivité hybride entre Skype entreprise Server et Skype entreprise online.
ms.openlocfilehash: ab7fb32c16e57e554c702a7b0f29ba350c1eedbe
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36160505"
---
# <a name="configure-hybrid-connectivity-between-skype-for-business-server-and-office-365"></a>Configuration de la connectivité hybride entre Skype entreprise Server et Office 365

**Résumé:** Consultez cette rubrique pour découvrir comment configurer la connectivité hybride entre Skype entreprise Server et teams ou Skype entreprise online.  La connectivité hybride vous permet de déplacer vos utilisateurs locaux vers teams ou Skype entreprise Online, tout en permettant à vos utilisateurs de tirer parti des services Cloud.
  
Avant d’effectuer les étapes décrites dans cette rubrique, vous devez disposer d’une [connectivité hybride plan de lecture entre Skype entreprise Server et Office 365](plan-hybrid-connectivity.md).
  
Le tableau suivant répertorie les tâches requises pour configurer la connectivité hybride Skype entreprise et fournit des liens vers les articles associés pour obtenir plus d’informations.
  
|Étape|Description|
|:-----|:-----|
|Créer un compte client pour Office 365   <br/> |Découvrez Office 365 sur [office 365](https://go.microsoft.com/fwlink/p/?LinkId=254980).  <br/> Pour vous assurer que votre environnement est prêt pour Office 365, reportez-vous à la [Configuration système requise](https://products.office.com/en-US/office-system-requirements).  <br/> Pour plus d’informations sur la configuration d’Office 365, voir [Getting Started with office 365](https://go.microsoft.com/fwlink/p/?LinkId=254982).  <br/> |
|Ajouter votre domaine à votre client Office 365 et vérifier la propriété  <br/> | Vous devez ajouter votre domaine à votre client Office 365, puis suivre les étapes pour valider le domaine avec Office 365. Cela permet de confirmer que vous êtes le propriétaire du domaine. <br/> Pour ajouter votre domaine à votre client Office 365, suivez les étapes décrites dans la rubrique [Ajouter un domaine à office 365](https://support.office.com/en-us/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US).  <br/> |
|Configuration de la synchronisation Active Directory  <br/> |La synchronisation Active Directory maintient la synchronisation permanente de votre Active Directory local avec Office 365. Cela vous permet de créer des versions synchronisées de chaque compte d’utilisateur et groupe.  <br/> <br> **Important:** Vous devez synchroniser les comptes AD de tous les utilisateurs de Skype entreprise de votre organisation entre vos déploiements locaux et en ligne, même si les utilisateurs ne sont pas déplacés vers teams ou Skype entreprise online. Si vous ne synchronisez pas tous les utilisateurs, la communication entre les utilisateurs locaux et les utilisateurs en ligne de votre organisation peut ne pas fonctionner comme prévu. Pour plus d’informations, reportez-vous à la rubrique [configurer Azure ad Connect pour les environnements hybrides](configure-azure-ad-connect.md).         |
| Configurer Skype entreprise hybride | Il existe trois étapes de base : <br><br> 1. Configurez votre environnement local de façon à ce qu’il se fédérer avec Office 365. <br> 2. Configurez votre environnement local pour qu’il approuve Office 365 et activez l’espace d’adressage SIP partagé avec Office 365.<br> 3. activez l’espace d’adressage SIP partagé dans votre client Office 365. <br><br> En outre, si vous disposez d’Exchange en local, vous pouvez configurer OAuth entre votre environnement Exchange local et Skype entreprise online. <br> <br>Pour plus d’informations, reportez-vous à la rubrique [configure Skype for Business Hybrid](configure-federation-with-skype-for-business-online.md).
|Déplacement des utilisateurs pilotes  <br/> |Une fois que vous avez terminé les étapes de préparation et de configuration de votre environnement pour teams ou Skype entreprise Online, vous pouvez commencer à transférer des utilisateurs pilotes vers votre client Office 365 en ligne. Pour plus d’informations, reportez-vous à la rubrique [déplacer des utilisateurs de sur site vers Skype entreprise Online](move-users-from-on-premises-to-skype-for-business-online.md) et [déplacer des utilisateurs de l’organisation locale vers teams](move-users-from-on-premises-to-Teams.md).  <br/> |