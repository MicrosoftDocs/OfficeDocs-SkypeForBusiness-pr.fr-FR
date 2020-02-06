---
title: Gestion des stratégies de conférence dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 34ec5e41-6fe6-450b-81b0-0d17b9989839
description: 'Résumé : Découvrez comment gérer les stratégies de conférence dans Skype entreprise Server.'
ms.openlocfilehash: fc069093b9cc7cf5ce0e1e1f1efc0ee9e18e335d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818645"
---
# <a name="manage-conferencing-policies-in-skype-for-business-server"></a>Gestion des stratégies de conférence dans Skype entreprise Server
 
**Résumé :** Apprenez à gérer les stratégies de conférence dans Skype entreprise Server.
  
Cette rubrique décrit comment gérer les stratégies de conférence. Pour plus d’informations sur la planification et le déploiement de conférences, voir [planifier les conférences dans Skype entreprise Server](../../plan-your-deployment/conferencing/conferencing.md) et [déployer des conférences dans Skype entreprise Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
  
Les stratégies de conférence vous permettent de définir une grande variété d’options de planification et de participation, allant de la possibilité d’inclure la fonction IP audio et vidéo dans une réunion à la détermination du nombre maximal de participants. Vous pouvez utiliser les stratégies de conférence pour gérer la sécurité, la bande passante et les aspects juridiques des réunions.
  
Vous pouvez définir une stratégie de conférence sur trois niveaux : étendue globale, étendue de site et étendue d’utilisateur. Les paramètres s’appliquent à un utilisateur spécifique de l’étendue la plus étroite à la plus large. Si vous affectez une stratégie à un utilisateur, les paramètres de cette stratégie prévalent. Si vous n’affectez pas une stratégie utilisateur à un utilisateur, les paramètres de la stratégie par site s’appliquent. Si vous n’appliquez aucune stratégie par utilisateur ou par site, la stratégie globale fournit les paramètres par défaut.
  
Une stratégie globale existe par défaut, par conséquent vous ne pouvez pas en créer une nouvelle. Vous ne pouvez pas non plus supprimer la stratégie globale existante, mais vous pouvez modifier la stratégie globale existante pour personnaliser les paramètres par défaut.
  
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Gestion des stratégies de conférence à l’aide du panneau de configuration Skype entreprise Server

Pour gérer les stratégies de conférence à l’aide du panneau de configuration Skype entreprise Server, procédez comme suit :
  
1. À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2.  Ouvrez le panneau de configuration Skype entreprise Server.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Stratégie de conférence**.
    
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Gestion des stratégies de conférence à l’aide de Skype entreprise Server Management Shell

Pour gérer les réunions à l’aide de Skype entreprise Server Management Shell, utilisez les applets de commande suivantes :
  
**Paramètres de stratégie de conférence**

|**Applet de commande**|**Description**|
|:-----|:-----|
|[Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |Renvoie des informations sur les stratégies de conférence qui ont été configurées pour être utilisées dans votre organisation.  <br/> |
|[Grant-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |Affecte une stratégie de conférence au niveau de l’étendue Utilisateur.  <br/> |
|[New-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |Crée une stratégie de conférence pour votre organisation.  <br/> |
|[Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |Supprime la stratégie de conférence spécifiée.  <br/> |
|[Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |Modifie une stratégie de conférence existante.  <br/> |
   

