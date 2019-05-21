---
title: Configuration de l’appareil création ou modification existante
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientPhoneCfgEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aac152bf-80e9-408a-9dbb-60d0843484ab
ROBOTS: NOINDEX, NOFOLLOW
description: Dans la page nouvelle configuration de l’appareil ou modifier la configuration de l’appareil, vous pouvez créer ou modifier un ensemble de paramètres permettant de gérer Skype entreprise Phone Edition. Ces paramètres vous permettent de configurer le mode de sécurité requis, le niveau de journalisation de l’appareil, les paramètres de qualité de service des communications vocales et de savoir si les téléphones doivent ou non se verrouiller automatiquement après une période d’inactivité donnée.
ms.openlocfilehash: 3d089fbecfe82367edf0ca375a262dc68896cfc4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34300342"
---
# <a name="device-configuration-create-new-or-edit-existing"></a><span data-ttu-id="02a78-104">Configuration du périphérique : création d’un périphérique ou modification d’un périphérique existant</span><span class="sxs-lookup"><span data-stu-id="02a78-104">Device Configuration: Create New or Edit Existing</span></span>
 
<span data-ttu-id="02a78-105">Dans la page **nouvelle configuration** de l’appareil ou **modifier la configuration** de l’appareil, vous pouvez créer ou modifier un ensemble de paramètres permettant de gérer Skype entreprise Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="02a78-105">On the **New Device Configuration** or **Edit Device Configuration** page, you can create or modify a collection of settings used to manage Skype for Business Phone Edition.</span></span> <span data-ttu-id="02a78-106">Ces paramètres vous permettent de configurer le mode de sécurité requis, le niveau de journalisation de l’appareil, les paramètres de qualité de service des communications vocales et de savoir si les téléphones doivent ou non se verrouiller automatiquement après une période d’inactivité donnée.</span><span class="sxs-lookup"><span data-stu-id="02a78-106">These settings enable you to configure such things as the required security mode, device logging level, Voice Quality of Service (QoS) settings, and whether or not phones should automatically lock after a specified period of inactivity.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="02a78-107">Tâches que vous pouvez effectuer</span><span class="sxs-lookup"><span data-stu-id="02a78-107">Tasks you can perform</span></span>

<span data-ttu-id="02a78-108">Dans la page **Nouvelle configuration de l’appareil** ou **Modifier la configuration de l’appareil**, vous pouvez effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="02a78-108">You can perform the following tasks on the **New Device Configuration** or **Edit Device Configuration** page:</span></span>
  
- <span data-ttu-id="02a78-109">Ajout d’une nouvelle configuration de l’appareil</span><span class="sxs-lookup"><span data-stu-id="02a78-109">Add a new device configuration.</span></span>
    
- <span data-ttu-id="02a78-110">Modification des propriétés d’une configuration d’appareil existante</span><span class="sxs-lookup"><span data-stu-id="02a78-110">Modify the properties of an existing device configuration.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="02a78-111">Référence d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="02a78-111">UI Reference</span></span>

<span data-ttu-id="02a78-112">Les listes ci-dessous décrivent les menus, les commandes, les champs et les propriétés de la page.</span><span class="sxs-lookup"><span data-stu-id="02a78-112">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="02a78-113">**Scope** Identifie l’étendue (globale ou site) de la configuration de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="02a78-113">**Scope** Identifies the scope (Global or Site) of the device configuration.</span></span>
    
- <span data-ttu-id="02a78-114">**Nom** Vous pouvez ajouter ou modifier le nom de la configuration de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="02a78-114">**Name** You can add or modify the name of the device configuration.</span></span>
    
- <span data-ttu-id="02a78-115">**Sécurité SIP** Vous pouvez configurer les exigences de transport et d’authentification pour les appareils Skype entreprise Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="02a78-115">**SIP security** You can configure transport and authentication requirements for Skype for Business Phone Edition devices.</span></span> <span data-ttu-id="02a78-116">Vous pouvez sélectionner l’une des options suivantes:</span><span class="sxs-lookup"><span data-stu-id="02a78-116">You can select from the following options:</span></span>
    
  - <span data-ttu-id="02a78-117">**Faible** Autorisez tout type d’autorisation ou de transport.</span><span class="sxs-lookup"><span data-stu-id="02a78-117">**Low** Allow any type of authorization or transport.</span></span>
    
  - <span data-ttu-id="02a78-118">**Moyenne** NTLM ou Kerberos est requis pour l’authentification des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="02a78-118">**Medium** NTLM or Kerberos is required for user authentication.</span></span>
    
  - <span data-ttu-id="02a78-119">**Elevé** NTLM ou Kerberos est requis pour l’authentification des utilisateurs et TLS est requis pour les connexions SIP.</span><span class="sxs-lookup"><span data-stu-id="02a78-119">**High** NTLM or Kerberos is required for user authentication and TLS is required for SIP connections.</span></span>
    
- <span data-ttu-id="02a78-120">**Niveau** de journalisation Vous pouvez activer la journalisation sur l’appareil UC.</span><span class="sxs-lookup"><span data-stu-id="02a78-120">**Logging level** You can enable logging on the UC device.</span></span> <span data-ttu-id="02a78-121">Valeurs valides: désactivé; Faiblesse PME et élevée.</span><span class="sxs-lookup"><span data-stu-id="02a78-121">Valid values are: Off; Low; Medium; and High.</span></span> <span data-ttu-id="02a78-122">La valeur par défaut est désactivé.</span><span class="sxs-lookup"><span data-stu-id="02a78-122">The default value is Off.</span></span>
    
- <span data-ttu-id="02a78-123">**Qualité de service (QoS) de qualité vocale** Vous pouvez spécifier la valeur DSCP affectée au trafic vocal émis à partir d’un appareil Skype entreprise Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="02a78-123">**Voice Quality of Service (QoS)** You can specify the DSCP value assigned to voice traffic emanating from a Skype for Business Phone Edition device.</span></span> <span data-ttu-id="02a78-124">Cependant, 40 n’est pas la valeur généralement utilisée pour le trafic audio.</span><span class="sxs-lookup"><span data-stu-id="02a78-124">The default is 40.</span></span> <span data-ttu-id="02a78-125">À la place, le trafic audio est presque toujours marqué avec le le code DSCP 46.</span><span class="sxs-lookup"><span data-stu-id="02a78-125">However, 40 is not the value typically used for audio traffic; instead, audio traffic is almost always marked with the DSCP code 46.</span></span> <span data-ttu-id="02a78-126">Pour maintenir une cohérence sur l’ensemble de votre réseau, vous pouvez remplacer cette valeur par 46.</span><span class="sxs-lookup"><span data-stu-id="02a78-126">In order to maintain consistency throughout your network, you might want to change this value to 46.</span></span>
    
- <span data-ttu-id="02a78-127">**Verrouillage du téléphone** Vous pouvez spécifier si les téléphones de communications unifiées se verrouillent automatiquement après une période d’inactivité spécifiée.</span><span class="sxs-lookup"><span data-stu-id="02a78-127">**Phone lock** You can specify whether or not UC phones will automatically lock themselves after a specified period of inactivity.</span></span> <span data-ttu-id="02a78-128">Vous pouvez configurer les paramètres suivants:</span><span class="sxs-lookup"><span data-stu-id="02a78-128">The following are the settings you can configure:</span></span>
    
  - <span data-ttu-id="02a78-129">**Mettre** en place le verrouillage d’appareil Vous pouvez mettre en place le verrouillage de l’appareil en cochant cette case.</span><span class="sxs-lookup"><span data-stu-id="02a78-129">**Enforce device locking** You can enforce device locking by selecting this check box.</span></span>
    
  - <span data-ttu-id="02a78-130">**Longueur minimale du code confidentiel** Vous pouvez spécifier la longueur minimale de votre code confidentiel (PIN) qui est utilisée pour déverrouiller le téléphone.</span><span class="sxs-lookup"><span data-stu-id="02a78-130">**Minimum PIN length** You can specify the minimum length for the personal identification number (PIN) that is used to unlock the phone.</span></span> <span data-ttu-id="02a78-131">La plage de la longueur du code confidentiel doit être comprise entre 4 et 15 chiffres.</span><span class="sxs-lookup"><span data-stu-id="02a78-131">The range for the PIN length is four to 15 digits.</span></span> <span data-ttu-id="02a78-132">La longueur par défaut est de six chiffres.</span><span class="sxs-lookup"><span data-stu-id="02a78-132">The default length is six digits.</span></span>
    
  - <span data-ttu-id="02a78-133">**Délai de verrouillage du téléphone** Vous pouvez spécifier la durée minimale avant le verrouillage du téléphone.</span><span class="sxs-lookup"><span data-stu-id="02a78-133">**Phone lock time-out** You can specify the minimum length of time before the phone locks itself.</span></span> <span data-ttu-id="02a78-134">La valeur par défaut est de 10 minutes.</span><span class="sxs-lookup"><span data-stu-id="02a78-134">The range for the time-out is 0 to 60 minutes; the default value is 10 minutes.</span></span> <span data-ttu-id="02a78-135">Le format de cette valeur est HH:MM:SS.</span><span class="sxs-lookup"><span data-stu-id="02a78-135">Enter the value in the format HH:MM:SS.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="02a78-136">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="02a78-136">See also</span></span>

[<span data-ttu-id="02a78-137">Configuration des périphériques</span><span class="sxs-lookup"><span data-stu-id="02a78-137">Device Configuration</span></span>](ms.lync.lscp.ClientDeviceCfgMain.md)

[<span data-ttu-id="02a78-138">Set-CsUCPhoneConfiguration</span><span class="sxs-lookup"><span data-stu-id="02a78-138">Set-CsUCPhoneConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps)
