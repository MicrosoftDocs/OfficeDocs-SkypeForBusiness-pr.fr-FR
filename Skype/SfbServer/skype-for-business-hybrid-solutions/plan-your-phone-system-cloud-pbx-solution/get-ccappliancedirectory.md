---
title: Get-CcApplianceDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c2fda202-db2f-4122-b630-7df11a697c5f
description: 'L’applet de commande Get-CcApplianceDirectory extrait l’annuaire de travail sur le serveur hôte de la version Cloud Connector de Skype Entreprise. Tous les fichier de déploiement sont recensés dans cet annuaire. '
ms.openlocfilehash: 77064676062411c3417e554e422b0ffaae461191
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003404"
---
# <a name="get-ccappliancedirectory"></a><span data-ttu-id="f8bcc-104">Get-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="f8bcc-104">Get-CcApplianceDirectory</span></span>
 
<span data-ttu-id="f8bcc-p102">L’applet de commande Get-CcApplianceDirectory extrait l’annuaire de travail sur le serveur hôte de la version Cloud Connector de Skype Entreprise. Tous les fichier de déploiement sont recensés dans cet annuaire. </span><span class="sxs-lookup"><span data-stu-id="f8bcc-p102">The Get-CcApplianceDirectory cmdlet retrieves the working directory on the Skype for Business Cloud Connector Edition host server. All deployment files are stored in this directory.</span></span> 
  
<span data-ttu-id="f8bcc-107">Cette applet de commande s’applique à Skype Entreprise, version Cloud Connector 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="f8bcc-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Get-CcApplianceDirectory
```

## <a name="parameters"></a><span data-ttu-id="f8bcc-108">Paramètres</span><span class="sxs-lookup"><span data-stu-id="f8bcc-108">Parameters</span></span>

<span data-ttu-id="f8bcc-109">Aucun</span><span class="sxs-lookup"><span data-stu-id="f8bcc-109">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="f8bcc-110">Exemples</span><span class="sxs-lookup"><span data-stu-id="f8bcc-110">Examples</span></span>
<span data-ttu-id="f8bcc-111"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="f8bcc-111"></span></span>

### <a name="example-1"></a><span data-ttu-id="f8bcc-112">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="f8bcc-112">Example 1</span></span>

<span data-ttu-id="f8bcc-113">L’exemple suivant montre le dossier actuel dans lequel sont stockés les fichiers de configuration et d’ordinateur virtuel des composants Cloud Connector :</span><span class="sxs-lookup"><span data-stu-id="f8bcc-113">The following example shows the current folder where configuration and virtual machine files of Cloud Connector components are stored:</span></span>
  
```powershell
Get-CcApplianceDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="f8bcc-114">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="f8bcc-114">Detailed Description</span></span>
<span data-ttu-id="f8bcc-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="f8bcc-115"></span></span>

<span data-ttu-id="f8bcc-116">L’applet de connexion Get-CcApplianceDirectory présente l’emplacement de stockage de tous les fichiers de configuration et d’ordinateur virtuel, journaux et certificats externes pour le périphérique Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="f8bcc-116">The Get-CcApplianceDirectory cmdlet shows where all configuration and virtual machine files, logs, and external certificates are stored for the Cloud Connector appliance.</span></span>
  
<span data-ttu-id="f8bcc-117">Chaque appareil Cloud Connector est doté de quatre composants : serveur de médiation, magasin de gestion central, serveur Edge et contrôleur de domaine.</span><span class="sxs-lookup"><span data-stu-id="f8bcc-117">Each Cloud Connector appliance has four components: Mediation Server, Central Management Store, Edge Server, and a Domain Controller.</span></span> <span data-ttu-id="f8bcc-118">Le dossier par défaut est\%C:\Users UserProfile%\CloudConnector\ApplianceRoot.</span><span class="sxs-lookup"><span data-stu-id="f8bcc-118">The default folder is C:\Users\%userprofile%\CloudConnector\ApplianceRoot.</span></span> <span data-ttu-id="f8bcc-119">Vous pouvez modifier ce dossier en utilisant l'applet de commande Set-CCApplianceDirectory.</span><span class="sxs-lookup"><span data-stu-id="f8bcc-119">You can change this folder by using the Set-CCApplianceDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="f8bcc-120">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="f8bcc-120">Input Types</span></span>
<span data-ttu-id="f8bcc-121"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f8bcc-121"></span></span>

<span data-ttu-id="f8bcc-p104">Aucun. L’applet de commande Get-CCApplianceDirectory n’accepte pas l’entrée redirigée.</span><span class="sxs-lookup"><span data-stu-id="f8bcc-p104">None. The Get-CCApplianceDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="f8bcc-124">Types de retours</span><span class="sxs-lookup"><span data-stu-id="f8bcc-124">Return Types</span></span>
<span data-ttu-id="f8bcc-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f8bcc-125"></span></span>

<span data-ttu-id="f8bcc-126">La commande renvoie un chemin d’accès de fichier.</span><span class="sxs-lookup"><span data-stu-id="f8bcc-126">The command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f8bcc-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f8bcc-127">See also</span></span>
<span data-ttu-id="f8bcc-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f8bcc-128"></span></span>

[<span data-ttu-id="f8bcc-129">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="f8bcc-129">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  

