---
title: Utiliser PowerShell pour contrôler l'accès invité à une équipe
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 11/09/17
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: sbhatta
search.appverid: MET150
description: Utilisez PowerShell pour autoriser ou bloquer l'accès invité aux équipes dans Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: e1e8eaa8722893316f761566a425b7e8ed6f2aaa
ms.sourcegitcommit: 454ded73af5854d7b81a3b996702a6464b3fc313
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/09/2019
ms.locfileid: "27772720"
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a>Utiliser PowerShell pour contrôler l'accès invité à une équipe
================================================

En plus d'utiliser le Centre d'administration d'Office 365 et le portail d'Azure Active Directory, vous pouvez utiliser Windows PowerShell pour contrôler l'accès invité. PowerShell permet d'effectuer les opérations suivantes :
  
- Autoriser ou bloquer l'accès invité à toutes les équipes et tous les groupes Office 365
    
  
- Autoriser l'ajout d'invités à toutes les équipes et tous les groupes Office 365
    
  
- Autoriser ou bloquer les utilisateurs invités d'une équipe ou d'un groupe Office 365 spécifique
    
  
Pour en savoir plus, consultez la section Utiliser PowerShell pour contrôler l'accès invité, dans l'onglet Gérer de l'[accès invité dans Groupes Office 365](https://support.office.com/article/Use-PowerShell-to-control-guest-access-bfc7a840-868f-4fd6-a390-f347bf51aff6#bkmk_usepowershell).
  
Vous pouvez également utiliser PowerShell pour autoriser ou bloquer un utilisateur invité en fonction de son domaine. Par exemple, votre entreprise, Contoso, a un partenariat avec une autre entreprise, Fabrikam. Vous pouvez ajouter Fabrikam à votre liste d'invités autorisés afin que vos utilisateurs puissent l'ajouter à leurs groupes. Pour plus d'informations, reportez-vous à la rubrique [Autoriser/bloquer l'accès invité aux groupes Office 365](https://go.microsoft.com/fwlink/?linkid=854001).
  
 
Si vous souhaitez bloquer l'accès invités dans Teams, mais autoriser les invités à accéder à des sites SharePoint, vous pouvez utiliser des applets de commande PowerShell Azure Active Directory pour désactiver le paramètre AllowGuestAccessToGroups sur l'objet Entreprise, en partant du principe que le partage externe est activé pour les sites SharePoint.   

