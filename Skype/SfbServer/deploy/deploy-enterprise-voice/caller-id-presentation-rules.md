---
title: Créer ou modifier une règle de traduction pour la présentation de l’ID d’appelant dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6a643961-a0a1-41d1-96ba-6c428a89d82e
description: 'Résumé : Découvrez comment configurer l’ID de l’appelant à l’aide du Panneau de configuration de Skype Entreprise Server.'
ms.openlocfilehash: ca1451a051a1c9053b88861222d2c4d42c5d555b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804184"
---
# <a name="create-or-modify-a-translation-rule-for-caller-id-presentation-in-skype-for-business-server"></a><span data-ttu-id="44ad0-103">Créer ou modifier une règle de traduction pour la présentation de l’ID d’appelant dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="44ad0-103">Create or modify a translation rule for caller ID presentation in Skype for Business Server</span></span>

<span data-ttu-id="44ad0-104">**Résumé :** Découvrez comment configurer l’ID de l’appelant à l’aide du Panneau de configuration de Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="44ad0-104">**Summary:** Learn how to configure Caller ID by using the Skype for Business Server Control Panel.</span></span>

<span data-ttu-id="44ad0-105">Avec Skype Entreprise Server, le numéro de téléphone de l’appelé (c’est-à-dire, le numéro de téléphone appelé)  peut être converti du format E.164 au format de numérotation local requis par l’homologue de la connexion (c’est-à-dire, la passerelle associée, le PBX ou la connexion SIP).</span><span class="sxs-lookup"><span data-stu-id="44ad0-105">With Skype for Business Server, the called party's phone number (that is, the phone number called) can be translated from E.164 format to the local dialing format that is required by the  _trunk peer_ (that is, the associated gateway, private branch exchange (PBX), or SIP trunk).</span></span> <span data-ttu-id="44ad0-106">Pour ce faire, vous devez définir une ou plusieurs règles de traduction pour traduire l’URI de demande avant de l’acheminer vers l’homologue de jonction.</span><span class="sxs-lookup"><span data-stu-id="44ad0-106">To do this, you must define one or more translation rules to translate the Request URI before routing it to the trunk peer.</span></span>

<span data-ttu-id="44ad0-107">Skype Entreprise Server vous permet également de traduire le numéro de téléphone de l’appelant (c’est-à-dire, le numéro de téléphone de l’appelant) du format E.164 au format de numérotation local requis par l’homologue de la connexion.</span><span class="sxs-lookup"><span data-stu-id="44ad0-107">Skype for Business Server also gives you the option to also translate the calling party's phone number (that is, the phone number that the caller is calling from) from E.164 format to the local dialing format that is required by the trunk peer.</span></span> <span data-ttu-id="44ad0-108">Par exemple, vous pouvez écrire une règle de traduction pour supprimer +44 au début d’une chaîne de numérotation et utiliser 0144 à la place.</span><span class="sxs-lookup"><span data-stu-id="44ad0-108">For example, you can write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>

### <a name="to-configure-caller-id-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="44ad0-109">Pour configurer l’ID de l’appelant à l’aide du Panneau de configuration de Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="44ad0-109">To configure Caller ID by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="44ad0-110">Ouvrez le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="44ad0-110">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="44ad0-111">Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Configuration de la jonction**.</span><span class="sxs-lookup"><span data-stu-id="44ad0-111">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

3. <span data-ttu-id="44ad0-112">Dans la page **Configuration de la jonction**, double-cliquez sur une jonction existante (par exemple, la jonction **Global**) pour afficher la boîte de dialogue **Modifier la configuration de la jonction**.</span><span class="sxs-lookup"><span data-stu-id="44ad0-112">On the **Trunk Configuration** page, double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>

4. <span data-ttu-id="44ad0-113">Pour configurer la présentation de l’identification de l’appelant :</span><span class="sxs-lookup"><span data-stu-id="44ad0-113">To configure caller ID presentation:</span></span>

   - <span data-ttu-id="44ad0-114">Pour choisir une ou plusieurs règles dans une liste de toutes les règles de traduction disponibles dans votre déploiement Voix Entreprise, cliquez sur **Sélectionner.**</span><span class="sxs-lookup"><span data-stu-id="44ad0-114">To choose one or more rules from a list of all translation rules available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="44ad0-115">Dans **Règles de traduction du numéro d’appel**, cliquez sur les règles que vous voulez associer à la jonction, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="44ad0-115">In **Calling number translation rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>

   - <span data-ttu-id="44ad0-116">Pour définir une nouvelle règle de traduction et l’associer à la jonction, cliquez sur **Nouvelle**.</span><span class="sxs-lookup"><span data-stu-id="44ad0-116">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="44ad0-117">Pour plus d’informations sur la définition d’une nouvelle règle, voir  [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) in the Deployment documentation.</span><span class="sxs-lookup"><span data-stu-id="44ad0-117">For details about defining a new rule, see  [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) in the Deployment documentation.</span></span>

   - <span data-ttu-id="44ad0-118">Pour modifier une règle de traduction associée à une jonction, cliquez sur son nom, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="44ad0-118">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="44ad0-119">Pour plus d’informations, voir [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="44ad0-119">For details, see [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) in the Deployment documentation.</span></span>

   - <span data-ttu-id="44ad0-120">Pour copier une règle de traduction existante qui servira de point de départ à la définition d’une nouvelle règle, cliquez sur son nom, sur **Copier**, puis sur **Coller**.</span><span class="sxs-lookup"><span data-stu-id="44ad0-120">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="44ad0-121">Pour plus d’informations, voir [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx).</span><span class="sxs-lookup"><span data-stu-id="44ad0-121">For details, see [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx).</span></span>

   - <span data-ttu-id="44ad0-122">Pour supprimer une règle de traduction d’une jonction, sélectionnez son nom, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="44ad0-122">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>

     > [!CAUTION]
     > <span data-ttu-id="44ad0-123">N’associez pas de règles de traduction à une configuration de jonction si vous avez configuré les règles de traduction sur l’homologue de jonction associé, car les deux règles risqueraient d’entrer en conflit.</span><span class="sxs-lookup"><span data-stu-id="44ad0-123">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>


