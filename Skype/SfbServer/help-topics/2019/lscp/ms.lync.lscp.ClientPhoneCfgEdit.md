---
title: Créer ou modifier une existant de la Configuration du périphérique
ms.reviewer: ''
ms.author: SerdarS
author: SerdarSoysal
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientPhoneCfgEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aac152bf-80e9-408a-9dbb-60d0843484ab
ROBOTS: NOINDEX, NOFOLLOW
description: Dans la page nouvelle Configuration de périphérique ou de modifier la Configuration du périphérique, vous pouvez créer ou modifier une collection de paramètres utilisés pour gérer les Skype pour Business Phone Edition. Ces paramètres vous permettent de configurer le mode de sécurité requis, le niveau de journalisation de l’appareil, les paramètres de qualité de service des communications vocales et de savoir si les téléphones doivent ou non se verrouiller automatiquement après une période d’inactivité donnée.
ms.openlocfilehash: 3dd7c9f782160b0f8a58d15e749276b4b2ee6adf
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32215814"
---
# <a name="device-configuration-create-new-or-edit-existing"></a><span data-ttu-id="6b984-104">Configuration du périphérique : création d’un périphérique ou modification d’un périphérique existant</span><span class="sxs-lookup"><span data-stu-id="6b984-104">Device Configuration: Create New or Edit Existing</span></span>
 
<span data-ttu-id="6b984-105">Dans la page **Nouvelle Configuration de périphérique** ou de **Modifier la Configuration du périphérique** , vous pouvez créer ou modifier une collection de paramètres utilisés pour gérer les Skype pour Business Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="6b984-105">On the **New Device Configuration** or **Edit Device Configuration** page, you can create or modify a collection of settings used to manage Skype for Business Phone Edition.</span></span> <span data-ttu-id="6b984-106">Ces paramètres vous permettent de configurer le mode de sécurité requis, le niveau de journalisation de l’appareil, les paramètres de qualité de service des communications vocales et de savoir si les téléphones doivent ou non se verrouiller automatiquement après une période d’inactivité donnée.</span><span class="sxs-lookup"><span data-stu-id="6b984-106">These settings enable you to configure such things as the required security mode, device logging level, Voice Quality of Service (QoS) settings, and whether or not phones should automatically lock after a specified period of inactivity.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="6b984-107">Tâches que vous pouvez effectuer</span><span class="sxs-lookup"><span data-stu-id="6b984-107">Tasks you can perform</span></span>

<span data-ttu-id="6b984-108">Dans la page **Nouvelle configuration de l’appareil** ou **Modifier la configuration de l’appareil**, vous pouvez effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="6b984-108">You can perform the following tasks on the **New Device Configuration** or **Edit Device Configuration** page:</span></span>
  
- <span data-ttu-id="6b984-109">Ajout d’une nouvelle configuration de l’appareil</span><span class="sxs-lookup"><span data-stu-id="6b984-109">Add a new device configuration.</span></span>
    
- <span data-ttu-id="6b984-110">Modification des propriétés d’une configuration d’appareil existante</span><span class="sxs-lookup"><span data-stu-id="6b984-110">Modify the properties of an existing device configuration.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="6b984-111">Référence d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="6b984-111">UI Reference</span></span>

<span data-ttu-id="6b984-112">Les listes ci-dessous décrivent les menus, les commandes, les champs et les propriétés de la page.</span><span class="sxs-lookup"><span data-stu-id="6b984-112">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="6b984-113">**Étendue** Identifie l’étendue (globale ou Site) de la configuration du périphérique.</span><span class="sxs-lookup"><span data-stu-id="6b984-113">**Scope** Identifies the scope (Global or Site) of the device configuration.</span></span>
    
- <span data-ttu-id="6b984-114">**Nom** Vous pouvez ajouter ou modifier le nom de la configuration du périphérique.</span><span class="sxs-lookup"><span data-stu-id="6b984-114">**Name** You can add or modify the name of the device configuration.</span></span>
    
- <span data-ttu-id="6b984-115">**Sécurité SIP** Vous pouvez configurer transport et authentification pour Skype pour les appareils de téléphone professionnel.</span><span class="sxs-lookup"><span data-stu-id="6b984-115">**SIP security** You can configure transport and authentication requirements for Skype for Business Phone Edition devices.</span></span> <span data-ttu-id="6b984-116">Vous pouvez sélectionner l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="6b984-116">You can select from the following options:</span></span>
    
  - <span data-ttu-id="6b984-117">**Faible** Autoriser n’importe quel type d’autorisation ou de transport.</span><span class="sxs-lookup"><span data-stu-id="6b984-117">**Low** Allow any type of authorization or transport.</span></span>
    
  - <span data-ttu-id="6b984-118">**Taille moyenne** NTLM ou Kerberos est requis pour l’authentification des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="6b984-118">**Medium** NTLM or Kerberos is required for user authentication.</span></span>
    
  - <span data-ttu-id="6b984-119">**Haute** NTLM ou Kerberos est requis pour l’authentification utilisateur et TLS est requis pour les connexions SIP.</span><span class="sxs-lookup"><span data-stu-id="6b984-119">**High** NTLM or Kerberos is required for user authentication and TLS is required for SIP connections.</span></span>
    
- <span data-ttu-id="6b984-120">**Niveau de journalisation** Vous pouvez activer l’enregistrement sur le périphérique de communications unifiées.</span><span class="sxs-lookup"><span data-stu-id="6b984-120">**Logging level** You can enable logging on the UC device.</span></span> <span data-ttu-id="6b984-121">Les valeurs valides sont : désactivé ; Faible ; Support ; et élevé.</span><span class="sxs-lookup"><span data-stu-id="6b984-121">Valid values are: Off; Low; Medium; and High.</span></span> <span data-ttu-id="6b984-122">La valeur par défaut est désactivé.</span><span class="sxs-lookup"><span data-stu-id="6b984-122">The default value is Off.</span></span>
    
- <span data-ttu-id="6b984-123">**Qualité de Service (QoS) de la voix** Vous pouvez spécifier la valeur DSCP attribuée pour le trafic vocal émanant d’un Skype pour appareil de téléphone professionnel.</span><span class="sxs-lookup"><span data-stu-id="6b984-123">**Voice Quality of Service (QoS)** You can specify the DSCP value assigned to voice traffic emanating from a Skype for Business Phone Edition device.</span></span> <span data-ttu-id="6b984-124">Cependant, 40 n’est pas la valeur généralement utilisée pour le trafic audio.</span><span class="sxs-lookup"><span data-stu-id="6b984-124">The default is 40.</span></span> <span data-ttu-id="6b984-125">À la place, le trafic audio est presque toujours marqué avec le le code DSCP 46.</span><span class="sxs-lookup"><span data-stu-id="6b984-125">However, 40 is not the value typically used for audio traffic; instead, audio traffic is almost always marked with the DSCP code 46.</span></span> <span data-ttu-id="6b984-126">Pour maintenir une cohérence sur l’ensemble de votre réseau, vous pouvez remplacer cette valeur par 46.</span><span class="sxs-lookup"><span data-stu-id="6b984-126">In order to maintain consistency throughout your network, you might want to change this value to 46.</span></span>
    
- <span data-ttu-id="6b984-127">**Verrouillage de téléphone** Vous pouvez spécifier ou non les téléphones UC seront eux-mêmes verrouillé automatiquement après une période d’inactivité.</span><span class="sxs-lookup"><span data-stu-id="6b984-127">**Phone lock** You can specify whether or not UC phones will automatically lock themselves after a specified period of inactivity.</span></span> <span data-ttu-id="6b984-128">Les paramètres que vous pouvez configurer sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="6b984-128">The following are the settings you can configure:</span></span>
    
  - <span data-ttu-id="6b984-129">**Appliquer le verrouillage de périphériques** Vous pouvez appliquer le verrouillage en activant cette case à cocher de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="6b984-129">**Enforce device locking** You can enforce device locking by selecting this check box.</span></span>
    
  - <span data-ttu-id="6b984-130">**Longueur minimale du code confidentiel** Vous pouvez spécifier la longueur minimale du code confidentiel (PIN) qui est utilisé pour déverrouiller le téléphone.</span><span class="sxs-lookup"><span data-stu-id="6b984-130">**Minimum PIN length** You can specify the minimum length for the personal identification number (PIN) that is used to unlock the phone.</span></span> <span data-ttu-id="6b984-131">La plage de la longueur du code confidentiel est quatre à 15 chiffres.</span><span class="sxs-lookup"><span data-stu-id="6b984-131">The range for the PIN length is four to 15 digits.</span></span> <span data-ttu-id="6b984-132">La longueur par défaut est de six chiffres.</span><span class="sxs-lookup"><span data-stu-id="6b984-132">The default length is six digits.</span></span>
    
  - <span data-ttu-id="6b984-133">**Délai d’expiration du verrouillage de téléphone** Vous pouvez spécifier la durée minimale avant les verrous de téléphone lui-même.</span><span class="sxs-lookup"><span data-stu-id="6b984-133">**Phone lock time-out** You can specify the minimum length of time before the phone locks itself.</span></span> <span data-ttu-id="6b984-134">La valeur par défaut est de 10 minutes.</span><span class="sxs-lookup"><span data-stu-id="6b984-134">The range for the time-out is 0 to 60 minutes; the default value is 10 minutes.</span></span> <span data-ttu-id="6b984-135">Le format de cette valeur est HH:MM:SS.</span><span class="sxs-lookup"><span data-stu-id="6b984-135">Enter the value in the format HH:MM:SS.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="6b984-136">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6b984-136">See also</span></span>

[<span data-ttu-id="6b984-137">Configuration des périphériques</span><span class="sxs-lookup"><span data-stu-id="6b984-137">Device Configuration</span></span>](ms.lync.lscp.ClientDeviceCfgMain.md)

[<span data-ttu-id="6b984-138">Set-CsUCPhoneConfiguration</span><span class="sxs-lookup"><span data-stu-id="6b984-138">Set-CsUCPhoneConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps)
