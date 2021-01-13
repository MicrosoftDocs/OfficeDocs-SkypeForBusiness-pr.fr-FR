---
title: 'Configuration de l’appareil : création d’une configuration ou modification d’un périphérique existant'
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientPhoneCfgEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: aac152bf-80e9-408a-9dbb-60d0843484ab
ROBOTS: NOINDEX, NOFOLLOW
description: Dans la page Nouvelle configuration d’appareil ou Modifier la configuration de l’appareil, vous pouvez créer ou modifier une collection de paramètres utilisés pour gérer Skype Entreprise Phone Edition. Ces paramètres vous permettent de configurer des choses telles que le mode de sécurité requis, le niveau de journalisation de périphérique, les paramètres de qualité de service des communications vocales et si les téléphones doivent ou non se verrouiller automatiquement après une période d’inactivité donnée.
ms.openlocfilehash: 0b330212c8dc050bb618f28ea6444b1c8e58f040
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830194"
---
# <a name="device-configuration-create-new-or-edit-existing"></a><span data-ttu-id="8ca19-104">Configuration de l’appareil : création d’une nouvelle ou modification d’une configuration existante</span><span class="sxs-lookup"><span data-stu-id="8ca19-104">Device Configuration: Create New or Edit Existing</span></span>
 
<span data-ttu-id="8ca19-105">Dans la page **Nouvelle configuration d’appareil** ou Modifier la **configuration** de l’appareil, vous pouvez créer ou modifier une collection de paramètres utilisés pour gérer Skype Entreprise Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="8ca19-105">On the **New Device Configuration** or **Edit Device Configuration** page, you can create or modify a collection of settings used to manage Skype for Business Phone Edition.</span></span> <span data-ttu-id="8ca19-106">Ces paramètres vous permettent de configurer des choses telles que le mode de sécurité requis, le niveau de journalisation de périphérique, les paramètres de qualité de service des communications vocales et si les téléphones doivent ou non se verrouiller automatiquement après une période d’inactivité donnée.</span><span class="sxs-lookup"><span data-stu-id="8ca19-106">These settings enable you to configure such things as the required security mode, device logging level, Voice Quality of Service (QoS) settings, and whether or not phones should automatically lock after a specified period of inactivity.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="8ca19-107">Tâches que vous pouvez effectuer</span><span class="sxs-lookup"><span data-stu-id="8ca19-107">Tasks you can perform</span></span>

<span data-ttu-id="8ca19-108">Vous pouvez effectuer les tâches suivantes dans la page **Nouvelle configuration de l’appareil** ou **Modifier la configuration de l’appareil** :</span><span class="sxs-lookup"><span data-stu-id="8ca19-108">You can perform the following tasks on the **New Device Configuration** or **Edit Device Configuration** page:</span></span>
  
- <span data-ttu-id="8ca19-109">Ajouter une nouvelle configuration de l’appareil</span><span class="sxs-lookup"><span data-stu-id="8ca19-109">Add a new device configuration.</span></span>
    
- <span data-ttu-id="8ca19-110">Modifier les propriétés d’une configuration d’appareil existante</span><span class="sxs-lookup"><span data-stu-id="8ca19-110">Modify the properties of an existing device configuration.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="8ca19-111">Référence d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="8ca19-111">UI Reference</span></span>

<span data-ttu-id="8ca19-112">Les listes suivantes décrivent les menus, commandes, champs et propriétés de la page.</span><span class="sxs-lookup"><span data-stu-id="8ca19-112">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="8ca19-113">**Étendue** Identifie l’étendue (globale ou site) de la configuration de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="8ca19-113">**Scope** Identifies the scope (Global or Site) of the device configuration.</span></span>
    
- <span data-ttu-id="8ca19-114">**Nom** Vous pouvez ajouter ou modifier le nom de la configuration de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="8ca19-114">**Name** You can add or modify the name of the device configuration.</span></span>
    
- <span data-ttu-id="8ca19-115">**Sécurité SIP** Vous pouvez configurer les exigences de transport et d’authentification pour les appareils Skype Entreprise Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="8ca19-115">**SIP security** You can configure transport and authentication requirements for Skype for Business Phone Edition devices.</span></span> <span data-ttu-id="8ca19-116">Vous pouvez sélectionner l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="8ca19-116">You can select from the following options:</span></span>
    
  - <span data-ttu-id="8ca19-117">**Faible** Autorisez tout type d’autorisation ou de transport.</span><span class="sxs-lookup"><span data-stu-id="8ca19-117">**Low** Allow any type of authorization or transport.</span></span>
    
  - <span data-ttu-id="8ca19-118">**Moyen** NTLM ou Kerberos est requis pour l’authentification des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="8ca19-118">**Medium** NTLM or Kerberos is required for user authentication.</span></span>
    
  - <span data-ttu-id="8ca19-119">**Élevé** NTLM ou Kerberos est requis pour l’authentification des utilisateurs et TLS est requis pour les connexions SIP.</span><span class="sxs-lookup"><span data-stu-id="8ca19-119">**High** NTLM or Kerberos is required for user authentication and TLS is required for SIP connections.</span></span>
    
- <span data-ttu-id="8ca19-120">**Niveau de journalisation** Vous pouvez activer la journalisation sur le périphérique UC.</span><span class="sxs-lookup"><span data-stu-id="8ca19-120">**Logging level** You can enable logging on the UC device.</span></span> <span data-ttu-id="8ca19-121">Les valeurs valides sont : Off; Faible ; Moyen ; et Élevé.</span><span class="sxs-lookup"><span data-stu-id="8ca19-121">Valid values are: Off; Low; Medium; and High.</span></span> <span data-ttu-id="8ca19-122">La valeur par défaut est Off.</span><span class="sxs-lookup"><span data-stu-id="8ca19-122">The default value is Off.</span></span>
    
- <span data-ttu-id="8ca19-123">**Qualité de service vocale (QoS)** Vous pouvez spécifier la valeur DSCP affectée au trafic vocal provenant d’un appareil Skype Entreprise Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="8ca19-123">**Voice Quality of Service (QoS)** You can specify the DSCP value assigned to voice traffic emanating from a Skype for Business Phone Edition device.</span></span> <span data-ttu-id="8ca19-124">La valeur par défaut est 40.</span><span class="sxs-lookup"><span data-stu-id="8ca19-124">The default is 40.</span></span> <span data-ttu-id="8ca19-125">Toutefois, 40 n’est pas la valeur généralement utilisée pour le trafic audio ; au lieu de cela, le trafic audio est presque toujours marqué avec le code DSCP 46.</span><span class="sxs-lookup"><span data-stu-id="8ca19-125">However, 40 is not the value typically used for audio traffic; instead, audio traffic is almost always marked with the DSCP code 46.</span></span> <span data-ttu-id="8ca19-126">Afin de maintenir la cohérence dans l’ensemble de votre réseau, vous pouvez modifier cette valeur sur 46.</span><span class="sxs-lookup"><span data-stu-id="8ca19-126">In order to maintain consistency throughout your network, you might want to change this value to 46.</span></span>
    
- <span data-ttu-id="8ca19-127">**Verrouillage du téléphone** Vous pouvez spécifier si les téléphones UC se verrouilleront automatiquement après une période d’inactivité spécifiée.</span><span class="sxs-lookup"><span data-stu-id="8ca19-127">**Phone lock** You can specify whether or not UC phones will automatically lock themselves after a specified period of inactivity.</span></span> <span data-ttu-id="8ca19-128">Les paramètres que vous pouvez configurer sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="8ca19-128">The following are the settings you can configure:</span></span>
    
  - <span data-ttu-id="8ca19-129">**Appliquer le verrouillage de l’appareil** Vous pouvez appliquer le verrouillage de l’appareil en cocher cette case.</span><span class="sxs-lookup"><span data-stu-id="8ca19-129">**Enforce device locking** You can enforce device locking by selecting this check box.</span></span>
    
  - <span data-ttu-id="8ca19-130">**Longueur minimale du code confidentiel** Vous pouvez spécifier la longueur minimale du code confidentiel utilisé pour déverrouiller le téléphone.</span><span class="sxs-lookup"><span data-stu-id="8ca19-130">**Minimum PIN length** You can specify the minimum length for the personal identification number (PIN) that is used to unlock the phone.</span></span> <span data-ttu-id="8ca19-131">Ce code peut être constitué de quatre à quinze chiffres.</span><span class="sxs-lookup"><span data-stu-id="8ca19-131">The range for the PIN length is four to 15 digits.</span></span> <span data-ttu-id="8ca19-132">La longueur par défaut est six chiffres.</span><span class="sxs-lookup"><span data-stu-id="8ca19-132">The default length is six digits.</span></span>
    
  - <span data-ttu-id="8ca19-133">**Délai d’verrouillage du téléphone** Vous pouvez spécifier la durée minimale avant que le téléphone ne se verrouille lui-même.</span><span class="sxs-lookup"><span data-stu-id="8ca19-133">**Phone lock time-out** You can specify the minimum length of time before the phone locks itself.</span></span> <span data-ttu-id="8ca19-134">Ce délai est compris entre 0 et 60 minutes ; la valeur par défaut est 10 minutes.</span><span class="sxs-lookup"><span data-stu-id="8ca19-134">The range for the time-out is 0 to 60 minutes; the default value is 10 minutes.</span></span> <span data-ttu-id="8ca19-135">Le format de cette valeur est HH:MM:SS.</span><span class="sxs-lookup"><span data-stu-id="8ca19-135">Enter the value in the format HH:MM:SS.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="8ca19-136">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8ca19-136">See also</span></span>

[<span data-ttu-id="8ca19-137">Configuration des périphériques</span><span class="sxs-lookup"><span data-stu-id="8ca19-137">Device Configuration</span></span>](ms.lync.lscp.ClientDeviceCfgMain.md)

[<span data-ttu-id="8ca19-138">Set-CsUCPhoneConfiguration</span><span class="sxs-lookup"><span data-stu-id="8ca19-138">Set-CsUCPhoneConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps)
