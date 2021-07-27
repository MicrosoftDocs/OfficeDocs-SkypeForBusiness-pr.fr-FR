---
title: Configurer la connectivité hybride | Déployer Skype Entreprise Server 2019 connect
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
description: Instructions d’implémentation de la connectivité hybride entre Skype Entreprise Server et Teams.
ms.openlocfilehash: 832aa989d8f698ac939dbf522476fb9dd6bfb2b8
ms.sourcegitcommit: 3f1635d1915561798ea764c3e33d7db55f7e49da
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/23/2021
ms.locfileid: "53574059"
---
# <a name="configure-hybrid-connectivity-between-skype-for-business-server-and-teams"></a>Configurer la connectivité hybride entre Skype Entreprise Server et Teams

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

**Résumé :** Lisez cette rubrique pour découvrir comment configurer la connectivité hybride entre Skype Entreprise Server et Teams.  La connectivité hybride vous permet de déplacer vos utilisateurs locaux vers Teams, et permet à vos utilisateurs de tirer parti des services cloud.
  
Avant d’effectuer les étapes de [cette](plan-hybrid-connectivity.md)rubrique, vous devez avoir lu Planifier la connectivité hybride entre Skype Entreprise Server et Teams .
  
Le tableau suivant répertorie les tâches requises pour configurer Skype Entreprise connectivité hybride et fournit des liens vers les articles associés pour plus d’informations.
  
|Étape|Description|
|:-----|:-----|
|Créer un compte client pour Microsoft 365   <br/> |Pour en savoir Microsoft 365, [Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=254980).  <br/> Pour vous assurer que votre environnement est prêt pour la Microsoft 365, consultez la [system requirements](https://products.office.com/office-system-requirements).  <br/> Pour plus d’informations sur la configuration de Microsoft 365, voir [Getting Started with Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=254982).  <br/> |
|Ajouter votre domaine à votre organisation Microsoft 365 et vérifier la propriété  <br/> | Vous devez ajouter votre domaine à votre organisation Microsoft 365, puis suivre les étapes pour valider le domaine avec Microsoft 365. Il s’agit de confirmer que vous êtes le propriétaire du domaine. <br/> Pour ajouter votre domaine à votre organisation Microsoft 365, suivez les étapes décrites dans Ajouter un domaine [à Microsoft 365](https://support.office.com/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US).  <br/> |
|Configurer la synchronisation Active Directory  <br/> |La synchronisation Active Directory conserve la synchronisation continue de votre annuaire Active Directory local avec Microsoft 365. Cela vous permet de créer des versions synchronisées de chaque compte d’utilisateur et groupe.  <br/> <br> **Important :** Vous devez synchroniser les comptes AD pour tous les utilisateurs Skype Entreprise de votre organisation entre vos déploiements locaux et en ligne, même si les utilisateurs ne sont pas déplacés vers Teams. Si vous ne synchronisez pas tous les utilisateurs, la communication entre les utilisateurs locaux et en ligne de votre organisation risque de ne pas fonctionner comme prévu. Pour plus d’informations, [voir Configurer azure ad Connecter pour les environnements hybrides.](configure-azure-ad-connect.md)         |
| Configurer Skype Entreprise hybride | Il existe trois étapes de base : <br><br> 1. Configurez votre environnement local pour la fédération avec Microsoft 365. <br> 2. Configurez votre environnement local pour qu’il Microsoft 365 et activez l’espace d’adressare SIP partagé avec Microsoft 365.<br> 3. Activez l’espace d’adressare SIP partagé dans Microsoft 365 organisation. <br><br> En outre, si vous Exchange local, vous pouvez configurer OAuth entre vos environnements Exchange local et en ligne. <br> <br>Pour plus d’informations, [voir Configurer Skype Entreprise hybride.](configure-federation-with-skype-for-business-online.md)
|Déplacer des utilisateurs pilotes  <br/> |Une fois que vous avez effectué les étapes de préparation et de configuration de votre environnement pour Teams, vous pouvez commencer à déplacer des utilisateurs pilotes vers votre organisation Microsoft 365 en ligne. Pour plus d’informations, voir [Move users from on premises to Teams](move-users-from-on-premises-to-Teams.md).  <br/> |
