---
title: Déploiements locaux de plusieurs forêts Skype Room System
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6793fca0-3970-44e4-8703-1925428c1967
description: Consultez cette rubrique pour apprendre à déployer Skype Room System dans un environnement local à plusieurs forêts.
ms.openlocfilehash: 7de5d285f36ddd1060ba53aa3e142a09a5d421e7
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234197"
---
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a><span data-ttu-id="9f477-103">Déploiements locaux de plusieurs forêts Skype Room System</span><span class="sxs-lookup"><span data-stu-id="9f477-103">Skype Room System multiple forest on-premises deployments</span></span>
 
<span data-ttu-id="9f477-104">Consultez cette rubrique pour apprendre à déployer Skype Room System dans un environnement local à plusieurs forêts.</span><span class="sxs-lookup"><span data-stu-id="9f477-104">Read this topic to learn how to deploy Skype Room System in a multiple forest on-premises environment.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9f477-105">Pour effectuer un déploiement dans plusieurs forêts, le système de salle Skype nécessite Exchange Server 2013 CU6 publiée le 26 août 2014.</span><span class="sxs-lookup"><span data-stu-id="9f477-105">In order to deploy in multiple forests, Skype Room System requires Exchange Server 2013 CU6 released on August 26, 2014.</span></span> <span data-ttu-id="9f477-106">Évitez d’utiliser une boîte aux lettres existante pour le système de salle Skype.</span><span class="sxs-lookup"><span data-stu-id="9f477-106">Avoid re-using an existing mailbox for Skype Room System.</span></span> <span data-ttu-id="9f477-107">Utiliser une nouvelle boîte aux lettres de ressources (supprimer l’ancienne boîte aux lettres et recréer) pour les systèmes de salle Skype.</span><span class="sxs-lookup"><span data-stu-id="9f477-107">Use a new (delete old mailbox and re-create) resource mailbox for Skype Room System.</span></span> <span data-ttu-id="9f477-108">Pour restaurer les réunions perdues en supprimant la boîte aux lettres, voir [connecter ou restaurer une boîte aux lettres supprimée](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="9f477-108">To restore the meetings lost by deleting the mailbox, see [Connect or restore a deleted mailbox](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx).</span></span> 
  
<span data-ttu-id="9f477-109">Après la création de la boîte aux lettres, vous pouvez utiliser Set-CalendarProcessing pour configurer la boîte aux lettres.</span><span class="sxs-lookup"><span data-stu-id="9f477-109">After creating the mailbox, you can use Set-CalendarProcessing to configure the mailbox.</span></span> <span data-ttu-id="9f477-110">Reportez-vous aux étapes 3 à 6 sous Déploiements locaux dans une forêt unique pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="9f477-110">Refer to steps 3 through 6 under Single forest on-premises deployments for more details.</span></span> <span data-ttu-id="9f477-111">Après la création d’une boîte aux lettres de ressources Exchange pour le système de salle Skype, activez le compte pour Skype entreprise en suivant les étapes de la rubrique activation de comptes de votre système de salle Skype pour Skype entreprise dans le cadre de déploiements locaux d’une seule forêt.</span><span class="sxs-lookup"><span data-stu-id="9f477-111">After creating an Exchange Resource mailbox for Skype Room System, enable the account for Skype for Business by following the steps in Enabling Skype Room System Accounts for Skype for Business under Single forest on-premises deployments.</span></span>
  
## <a name="option-1-create-a-new-resource-mailbox"></a><span data-ttu-id="9f477-112">Option 1 : créer une nouvelle boîte aux lettres de ressources</span><span class="sxs-lookup"><span data-stu-id="9f477-112">Option 1: Create a new resource mailbox</span></span>

<span data-ttu-id="9f477-113">Pour déployer le système de salle Skype dans un environnement multiforêt:</span><span class="sxs-lookup"><span data-stu-id="9f477-113">To deploy Skype Room System in a multi-forest environment:</span></span>
  
1. <span data-ttu-id="9f477-114">Créez un utilisateur lié (LinkedRoomTest) dans Active Directory (forêt d’authentification).</span><span class="sxs-lookup"><span data-stu-id="9f477-114">Create a Linked User (LinkedRoomTest) in Active Directory (Authentication Forest).</span></span>
    
2. <span data-ttu-id="9f477-115">Exécutez les commandes suivantes dans le Exchange Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="9f477-115">Run the following commands in the Exchange Server Management Shell:</span></span>
    
   ```
   $cred = Get-Credential AuthForest\LinkedRoomTest
   new-mailbox -Alias LinkedRoomTest -LinkedMasterAccount AuthForest\LinkedRoomTest -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -UserPrincipalName LinkedRoomTest@ExchangeForest.contoso.comm -Name LinkedRoomTest -LinkedCredential $cred -LinkedRoom
   ```

## <a name="option-2-change-an-existing-room-mailbox-to-skype-room-system-linked-resource-mailbox"></a><span data-ttu-id="9f477-116">Option 2: remplacer une boîte aux lettres de salle existante par une boîte aux lettres de ressources liée au système de salle Skype</span><span class="sxs-lookup"><span data-stu-id="9f477-116">Option 2: Change an existing room mailbox to Skype Room System (linked) resource mailbox</span></span>

```
$cred=Get-Credential AuthForest\LinkedRoomTest1
Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
```


