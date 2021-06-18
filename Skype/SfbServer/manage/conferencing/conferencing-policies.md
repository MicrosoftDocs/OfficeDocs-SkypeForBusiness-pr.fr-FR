---
title: Gérer les stratégies de conférence dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 34ec5e41-6fe6-450b-81b0-0d17b9989839
description: 'Résumé : Découvrez comment gérer les stratégies de conférence dans Skype Entreprise Server.'
ms.openlocfilehash: 39855aac09b88852d0931c9b8fbdb8e2e9187c71
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099100"
---
# <a name="manage-conferencing-policies-in-skype-for-business-server"></a>Gérer les stratégies de conférence dans Skype Entreprise Server
 
**Résumé :** Découvrez comment gérer les stratégies de conférence dans Skype Entreprise Server.
  
Cette rubrique décrit comment gérer les stratégies de conférence. Pour plus d’informations sur la façon de planifier et de déployer la conférence, voir [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) and Deploy [conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
  
Les stratégies de conférence vous permettent de définir un large éventail d’options de planification et de participation, allant de l’option d’accès audio et vidéo IP à la participation maximale. Vous pouvez utiliser des stratégies de conférence pour gérer la sécurité, la bande passante et les aspects juridiques des réunions.
  
Vous pouvez définir une stratégie de conférence sur trois niveaux : étendue globale, étendue de site et étendue d’utilisateur. Les paramètres s’appliquent à un utilisateur de l’étendue la plus étroite à la plus large. Si vous affectez une stratégie à un utilisateur, ces paramètres sont prioritaires. Si vous n’affectez pas une stratégie utilisateur à un utilisateur, les paramètres de la stratégie par site s’appliquent. Si vous n’appliquez aucune stratégie par utilisateur ou par site, la stratégie globale fournit les paramètres par défaut.
  
Une stratégie globale existe par défaut, par conséquent vous ne pouvez pas en créer une nouvelle. Vous ne pouvez pas non plus supprimer la stratégie globale existante, mais vous pouvez modifier la stratégie globale existante pour personnaliser les paramètres par défaut.
  
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Gérer les stratégies de conférence à l’aide du Panneau de contrôle Skype Entreprise Server

Pour gérer les stratégies de conférence à l’aide du Panneau de contrôle Skype Entreprise Server :
  
1. Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.
    
2.  Ouvrez le Panneau de contrôle Skype Entreprise Server.
    
3. Dans la barre de navigation de gauche, **cliquez** sur Conférence, puis sur Stratégie **de conférence.**
    
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Gérer les stratégies de conférence à l’aide de Skype Entreprise Server Management Shell

Pour gérer les réunions à l’aide de Skype Entreprise Server Management Shell, utilisez les cmdlets suivantes :
  
**Paramètres de stratégie de conférence**

|**Applet de commande**|**Description**|
|:-----|:-----|
|[Get-CsConferencingPolicy](/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |Renvoie des informations sur les stratégies de conférence qui ont été configurées pour être utilisées dans votre organisation.  <br/> |
|[Grant-CsConferencingPolicy](/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |Affecte une stratégie de conférence au niveau de l’étendue Utilisateur.  <br/> |
|[New-CsConferencingPolicy](/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |Crée une stratégie de conférence à utiliser dans votre organisation.  <br/> |
|[Remove-CsConferencingPolicy](/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |Supprime la stratégie de conférence spécifiée.  <br/> |
|[Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |Modifie une stratégie de conférence existante.  <br/> |
