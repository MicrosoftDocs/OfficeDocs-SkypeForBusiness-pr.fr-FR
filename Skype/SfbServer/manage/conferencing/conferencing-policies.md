---
title: Gestion des stratégies de conférence dans Skype Entreprise Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 34ec5e41-6fe6-450b-81b0-0d17b9989839
description: 'Résumé : Apprenez à gérer les stratégies de conférence dans Skype pour Business Server 2015.'
ms.openlocfilehash: 48ae623a9571b848ccb70b377416343eccca0c1c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="manage-conferencing-policies-in-skype-for-business-server-2015"></a>Gestion des stratégies de conférence dans Skype Entreprise Server 2015
 
**Résumé :** Découvrez comment gérer les stratégies de conférence dans Skype pour Business Server 2015.
  
Cette rubrique décrit comment gérer les stratégies de conférence. Pour plus d’informations sur la façon de planifier et de déployer des conférences, voir [conférences de déployer dans Skype pour Business Server 2015](../../deploy/deploy-conferencing/deploy-conferencing.md)et de [Plan pour les conférences dans Skype pour Business Server 2015](../../plan-your-deployment/conferencing/conferencing.md) .
  
Les stratégies de conférence vous permettent de définir une grande variété d’options de planification et de participation, allant de la possibilité d’inclure la fonction IP audio et vidéo dans une réunion à la détermination du nombre maximal de participants. Vous pouvez utiliser les stratégies de conférence pour gérer la sécurité, la bande passante et les aspects juridiques des réunions.
  
Vous pouvez définir une stratégie de conférence sur trois niveaux : étendue globale, étendue de site et étendue d’utilisateur. Les paramètres s’appliquent à un utilisateur spécifique de l’étendue la plus étroite à la plus large. Si vous affectez une stratégie à un utilisateur, les paramètres de cette stratégie prévalent. Si vous n’affectez pas une stratégie utilisateur à un utilisateur, les paramètres de la stratégie par site s’appliquent. Si vous n’appliquez aucune stratégie par utilisateur ou par site, la stratégie globale fournit les paramètres par défaut.
  
Une stratégie globale existe par défaut, par conséquent vous ne pouvez pas en créer une nouvelle. Vous ne pouvez pas non plus supprimer la stratégie globale existante, mais vous pouvez modifier la stratégie globale existante pour personnaliser les paramètres par défaut.
  
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Gérer les stratégies de conférence pour le panneau de configuration de Business Server à l’aide de Skype

Pour gérer les stratégies de la conférence à l’aide de Skype pour le panneau de configuration de Business Server :
  
1. À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2.  Ouvrez Skype pour le panneau de configuration de Business Server.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Stratégie de conférence**.
    
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Gérer les stratégies de la conférence à l’aide de Skype pour Business Server Management Shell

Pour gérer des réunions à l’aide de Skype pour Business Server Management Shell, utilisez les applets de commande suivantes :
  
**Paramètres de stratégie de conférence**

|**Applet de commande**|**Description**|
|:-----|:-----|
|[Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |Renvoie des informations sur les stratégies de conférence qui ont été configurées pour être utilisées dans votre organisation.  <br/> |
|[Grant-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |Affecte une stratégie de conférence au niveau de l’étendue Utilisateur.  <br/> |
|[Nouvelle-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |Crée une stratégie de conférence pour votre organisation.  <br/> |
|[Supprimer-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |Supprime la stratégie de conférence spécifiée.  <br/> |
|[Ensemble-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |Modifie une stratégie de conférence existante.  <br/> |
   

