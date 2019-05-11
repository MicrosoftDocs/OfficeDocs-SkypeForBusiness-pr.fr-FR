---
title: Utiliser PowerShell pour contrôler l'accès invité à une équipe
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 11/09/17
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: Utilisez PowerShell pour autoriser ou bloquer l'accès invité aux équipes dans Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 815a35efbce89404b012d5534e257752bef8d53e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33886381"
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a>Utiliser PowerShell pour contrôler l'accès invité à une équipe
================================================

Outre l’utilisation du centre d’administration Microsoft 365 et le portail d’Azure Active Directory, vous pouvez utiliser Windows PowerShell pour contrôler l’accès invité. PowerShell permet d'effectuer les opérations suivantes :
  
- Autoriser ou bloquer l'accès invité à toutes les équipes et tous les groupes Office 365
    
- Autoriser l'ajout d'invités à toutes les équipes et tous les groupes Office 365
      
- Autoriser ou bloquer les utilisateurs invités d'une équipe ou d'un groupe Office 365 spécifique
    
Pour plus d’informations, consultez la section « Utilisation de PowerShell pour contrôler l’accès invité » sous l’onglet Gestion de [l’accès invité dans Office 365 groupes](https://support.office.com/article/Use-PowerShell-to-control-guest-access-bfc7a840-868f-4fd6-a390-f347bf51aff6#bkmk_usepowershell).
  
Vous pouvez également utiliser PowerShell pour autoriser ou bloquer un utilisateur invité en fonction de son domaine. Par exemple, votre entreprise, Contoso, a un partenariat avec une autre entreprise, Fabrikam. Vous pouvez ajouter Fabrikam à votre liste d'invités autorisés afin que vos utilisateurs puissent l'ajouter à leurs groupes. Pour plus d'informations, reportez-vous à la rubrique [Autoriser/bloquer l'accès invité aux groupes Office 365](https://go.microsoft.com/fwlink/?linkid=854001).
  
Si vous souhaitez bloquer les invités dans les équipes et que vous souhaitez tout de même les autoriser à accéder aux sites SharePoint, vous pouvez utiliser les applets de commande Windows Azure Active Directory Powershell pour désactiver le paramètre AllowGuestsToAccessGroups sur l’objet de la société, en supposant que le partage externe est activé pour Sites SharePoint.   

## <a name="guest-access-vs-external-access"></a>Accès invité et l’accès externe

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]
