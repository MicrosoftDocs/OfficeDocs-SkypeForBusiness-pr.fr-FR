---
title: Créer de nouvelles ou modifier les existants de la Configuration du périphérique
ms.author: laurawi
author: LauraWi
manager: serdars
ms.date: 3/23/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientPhoneCfgEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aac152bf-80e9-408a-9dbb-60d0843484ab
description: Dans la page nouvelle Configuration de périphérique ou de modifier la Configuration de périphérique, vous pouvez créer ou modifier une collection de paramètres utilisés pour gérer le Skype pour téléphone professionnel. Ces paramètres vous permettent de configurer des éléments, comme le mode de sécurité nécessaire, le niveau de journalisation de l’appareil, les paramètres de qualité de service des communications vocales et le verrouillage automatique ou non des téléphones après une période d’inactivité spécifiée.
ms.openlocfilehash: c6d8f291b6602ad41ca2942e2d4b507d2727bcd1
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="device-configuration-create-new-or-edit-existing"></a><span data-ttu-id="27296-104">Configuration du périphérique : création d’un périphérique ou modification d’un périphérique existant</span><span class="sxs-lookup"><span data-stu-id="27296-104">Device Configuration: Create New or Edit Existing</span></span>
 
<span data-ttu-id="27296-105">Dans la page **Nouvelle Configuration de périphérique** ou de **Modifier la Configuration de périphérique** , vous pouvez créer ou modifier une collection de paramètres utilisés pour gérer le Skype pour téléphone professionnel.</span><span class="sxs-lookup"><span data-stu-id="27296-105">On the **New Device Configuration** or **Edit Device Configuration** page, you can create or modify a collection of settings used to manage Skype for Business Phone Edition.</span></span> <span data-ttu-id="27296-106">Ces paramètres vous permettent de configurer des éléments, comme le mode de sécurité nécessaire, le niveau de journalisation de l’appareil, les paramètres de qualité de service des communications vocales et le verrouillage automatique ou non des téléphones après une période d’inactivité spécifiée.</span><span class="sxs-lookup"><span data-stu-id="27296-106">These settings enable you to configure such things as the required security mode, device logging level, Voice Quality of Service (QoS) settings, and whether or not phones should automatically lock after a specified period of inactivity.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="27296-107">Tâches que vous pouvez effectuer</span><span class="sxs-lookup"><span data-stu-id="27296-107">Tasks you can perform</span></span>

<span data-ttu-id="27296-108">Dans la page **Nouvelle configuration de l’appareil** ou **Modifier la configuration de l’appareil**, vous pouvez effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="27296-108">You can perform the following tasks on the **New Device Configuration** or **Edit Device Configuration** page:</span></span>
  
- <span data-ttu-id="27296-109">Ajout d’une nouvelle configuration de l’appareil</span><span class="sxs-lookup"><span data-stu-id="27296-109">Add a new device configuration.</span></span>
    
- <span data-ttu-id="27296-110">Modification des propriétés d’une configuration d’appareil existante</span><span class="sxs-lookup"><span data-stu-id="27296-110">Modify the properties of an existing device configuration.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="27296-111">Référence d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="27296-111">UI Reference</span></span>

<span data-ttu-id="27296-112">Les listes ci-dessous décrivent les menus, les commandes, les champs et les propriétés de la page.</span><span class="sxs-lookup"><span data-stu-id="27296-112">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="27296-113">**Champ d’application** Identifie la portée (Global ou Site) de la configuration du périphérique.</span><span class="sxs-lookup"><span data-stu-id="27296-113">**Scope** Identifies the scope (Global or Site) of the device configuration.</span></span>
    
- <span data-ttu-id="27296-114">**Nom** Vous pouvez ajouter ou modifier le nom de la configuration du périphérique.</span><span class="sxs-lookup"><span data-stu-id="27296-114">**Name** You can add or modify the name of the device configuration.</span></span>
    
- <span data-ttu-id="27296-115">**Sécurité de SIP** Vous pouvez configurer les exigences de transport et d’authentification pour Skype pour les dispositifs de téléphone professionnel.</span><span class="sxs-lookup"><span data-stu-id="27296-115">**SIP security** You can configure transport and authentication requirements for Skype for Business Phone Edition devices.</span></span> <span data-ttu-id="27296-116">Vous pouvez sélectionner parmi les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="27296-116">You can select from the following options:</span></span>
    
  - <span data-ttu-id="27296-117">**Faible** Autoriser n’importe quel type d’autorisation ou de transport.</span><span class="sxs-lookup"><span data-stu-id="27296-117">**Low** Allow any type of authorization or transport.</span></span>
    
  - <span data-ttu-id="27296-118">**Support** NTLM ou Kerberos est requis pour l’authentification des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="27296-118">**Medium** NTLM or Kerberos is required for user authentication.</span></span>
    
  - <span data-ttu-id="27296-119">**Élevé** NTLM ou Kerberos est requis pour l’authentification des utilisateurs et TLS est requis pour les connexions de SIP.</span><span class="sxs-lookup"><span data-stu-id="27296-119">**High** NTLM or Kerberos is required for user authentication and TLS is required for SIP connections.</span></span>
    
- <span data-ttu-id="27296-120">**Niveau d’enregistrement** Vous pouvez activer la journalisation sur le périphérique de communications unifiées.</span><span class="sxs-lookup"><span data-stu-id="27296-120">**Logging level** You can enable logging on the UC device.</span></span> <span data-ttu-id="27296-121">Les valeurs valides sont : Off ; Faible ; Support ; et haute.</span><span class="sxs-lookup"><span data-stu-id="27296-121">Valid values are: Off; Low; Medium; and High.</span></span> <span data-ttu-id="27296-122">La valeur par défaut est désactivé.</span><span class="sxs-lookup"><span data-stu-id="27296-122">The default value is Off.</span></span>
    
- <span data-ttu-id="27296-123">**Qualité de la voix de Service (QoS)** Vous pouvez spécifier la valeur DSCP du trafic de voix à partir d’un Skype pour dispositif de téléphone professionnel.</span><span class="sxs-lookup"><span data-stu-id="27296-123">**Voice Quality of Service (QoS)** You can specify the DSCP value assigned to voice traffic emanating from a Skype for Business Phone Edition device.</span></span> <span data-ttu-id="27296-124">Cependant, 40 n’est pas la valeur généralement utilisée pour le trafic audio.</span><span class="sxs-lookup"><span data-stu-id="27296-124">The default is 40.</span></span> <span data-ttu-id="27296-125">À la place, le trafic audio est presque toujours marqué avec le le code DSCP 46.</span><span class="sxs-lookup"><span data-stu-id="27296-125">However, 40 is not the value typically used for audio traffic; instead, audio traffic is almost always marked with the DSCP code 46.</span></span> <span data-ttu-id="27296-126">Pour maintenir une cohérence sur l’ensemble de votre réseau, vous pouvez remplacer cette valeur par 46.</span><span class="sxs-lookup"><span data-stu-id="27296-126">In order to maintain consistency throughout your network, you might want to change this value to 46.</span></span>
    
- <span data-ttu-id="27296-127">**Verrouiller le Tél.** Vous pouvez spécifier ou non des téléphones de communications unifiées seront eux-mêmes verrouiller automatiquement après une période d’inactivité spécifiée.</span><span class="sxs-lookup"><span data-stu-id="27296-127">**Phone lock** You can specify whether or not UC phones will automatically lock themselves after a specified period of inactivity.</span></span> <span data-ttu-id="27296-128">Les paramètres que vous pouvez configurer sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="27296-128">The following are the settings you can configure:</span></span>
    
  - <span data-ttu-id="27296-129">**Appliquer le verrouillage de périphérique** Vous pouvez appliquer le dispositif de verrouillage en activant cette case à cocher.</span><span class="sxs-lookup"><span data-stu-id="27296-129">**Enforce device locking** You can enforce device locking by selecting this check box.</span></span>
    
  - <span data-ttu-id="27296-130">**Longueur de la broche de minimum** Vous pouvez spécifier la longueur minimale pour le numéro d’identification personnel (PIN) qui est utilisé pour déverrouiller le téléphone.</span><span class="sxs-lookup"><span data-stu-id="27296-130">**Minimum PIN length** You can specify the minimum length for the personal identification number (PIN) that is used to unlock the phone.</span></span> <span data-ttu-id="27296-131">La plage de la longueur du code confidentiel est de quatre à 15 chiffres.</span><span class="sxs-lookup"><span data-stu-id="27296-131">The range for the PIN length is four to 15 digits.</span></span> <span data-ttu-id="27296-132">La longueur par défaut est six chiffres.</span><span class="sxs-lookup"><span data-stu-id="27296-132">The default length is six digits.</span></span>
    
  - <span data-ttu-id="27296-133">**Délai d’attente du verrou de téléphone** Vous pouvez spécifier la durée minimale avant les verrous de téléphone lui-même.</span><span class="sxs-lookup"><span data-stu-id="27296-133">**Phone lock time-out** You can specify the minimum length of time before the phone locks itself.</span></span> <span data-ttu-id="27296-134">La valeur par défaut est de 10 minutes.</span><span class="sxs-lookup"><span data-stu-id="27296-134">The range for the time-out is 0 to 60 minutes; the default value is 10 minutes.</span></span> <span data-ttu-id="27296-135">Le format de cette valeur est HH:MM:SS.</span><span class="sxs-lookup"><span data-stu-id="27296-135">Enter the value in the format HH:MM:SS.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="27296-136">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="27296-136">See also</span></span>

#### 

[<span data-ttu-id="27296-137">Configuration du périphérique</span><span class="sxs-lookup"><span data-stu-id="27296-137">Device Configuration</span></span>](device-configuration.md)
#### 

[<span data-ttu-id="27296-138">Ensemble-CsUCPhoneConfiguration</span><span class="sxs-lookup"><span data-stu-id="27296-138">Set-CsUCPhoneConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps)

