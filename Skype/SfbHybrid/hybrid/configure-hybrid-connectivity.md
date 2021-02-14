---
title: Configurer la connectivité hybride | Déploiement de la connexion à Skype Entreprise Server 2019
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Instructions pour l’implémentation de la connectivité hybride entre Skype Entreprise Server et Skype Entreprise Online.
ms.openlocfilehash: 3a68d39062387952b7a43bb22599265a69bf7a61
ms.sourcegitcommit: 80b66127b3415c99f9468625add6a8f2c36bca74
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/07/2020
ms.locfileid: "48376747"
---
# <a name="configure-hybrid-connectivity-between-skype-for-business-server-and-office-365"></a>Configurer la connectivité hybride entre Skype Entreprise Server et Office 365.

**Résumé :** Lisez cette rubrique pour découvrir comment configurer la connectivité hybride entre Skype Entreprise Server et Teams ou Skype Entreprise Online.  La connectivité hybride vous permet de déplacer vos utilisateurs locaux vers Teams ou Skype Entreprise Online, et permet à vos utilisateurs de tirer parti des services cloud.
  
Avant d’effectuer les étapes de cette rubrique, vous devez avoir lu Planifier la connectivité hybride entre Skype Entreprise [Server et Office 365.](plan-hybrid-connectivity.md)
  
Le tableau suivant répertorie les tâches requises pour configurer la connectivité hybride de Skype Entreprise et fournit des liens vers les articles associés pour plus d’informations.
  
|Étape|Description|
|:-----|:-----|
|Créer un compte client pour Office 365   <br/> |Découvrez Office 365 sur [Office 365.](https://go.microsoft.com/fwlink/p/?LinkId=254980)  <br/> Pour vous assurer que votre environnement est prêt pour Office 365, consultez la [system requirements](https://products.office.com/office-system-requirements).  <br/> Pour plus d’informations sur la configuration d’Office 365, voir [Getting Started with Office 365](https://go.microsoft.com/fwlink/p/?LinkId=254982).  <br/> |
|Ajouter votre domaine à votre organisation Office 365 et vérifier la propriété  <br/> | Vous devez ajouter votre domaine à votre organisation Office 365, puis suivre les étapes pour valider le domaine avec Office 365. Il s’agit de confirmer que vous êtes le propriétaire du domaine. <br/> Pour ajouter votre domaine à votre organisation Office 365, suivez les étapes décrites dans Ajouter un domaine [à Office 365.](https://support.office.com/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US)  <br/> |
|Configurer la synchronisation Active Directory  <br/> |La synchronisation Active Directory conserve la synchronisation continue de votre annuaire Active Directory local avec Office 365. Cela vous permet de créer des versions synchronisées de chaque compte d’utilisateur et groupe.  <br/> <br> **Important :** Vous devez synchroniser les comptes AD pour tous les utilisateurs Skype Entreprise de votre organisation entre vos déploiements locaux et en ligne, même si les utilisateurs ne sont pas déplacés vers Teams ou Skype Entreprise Online. Si vous ne synchronisez pas tous les utilisateurs, la communication entre les utilisateurs locaux et en ligne de votre organisation risque de ne pas fonctionner comme prévu. Pour plus d’informations, [voir Configurer Azure AD Connect pour les environnements hybrides.](configure-azure-ad-connect.md)         |
| Configurer Skype Entreprise hybride | Il existe trois étapes de base : <br><br> 1. Configurez votre environnement local pour la fédération avec Office 365. <br> 2. Configurez votre environnement local pour qu’il truste Office 365 et activez l’espace d’adressare SIP partagé avec Office 365.<br> 3. Activez l’espace d’adressare SIP partagé dans votre organisation Office 365. <br><br> De plus, si vous avez Exchange en local, vous pouvez configurer OAuth entre vos environnements Exchange local et Skype Entreprise Online. <br> <br>Pour plus d’informations, [voir Configurer Skype Entreprise hybride.](configure-federation-with-skype-for-business-online.md)
|Déplacer des utilisateurs pilotes  <br/> |Une fois que vous avez terminé les étapes de préparation et de configuration de votre environnement pour Teams ou Skype Entreprise Online, vous pouvez commencer à déplacer des utilisateurs pilotes vers votre organisation Office 365 en ligne. Pour plus d’informations, voir [Move users from on premises to Skype for Business Online](move-users-from-on-premises-to-skype-for-business-online.md) and Move users from on [premises to Teams](move-users-from-on-premises-to-Teams.md).  <br/> |
