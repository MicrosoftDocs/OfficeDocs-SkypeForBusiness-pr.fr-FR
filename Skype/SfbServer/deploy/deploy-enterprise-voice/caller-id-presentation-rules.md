---
title: Créer ou modifier une règle de traduction pour la présentation des ID de l’appelant dans Skype pour Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6a643961-a0a1-41d1-96ba-6c428a89d82e
description: 'Résumé : Découvrez comment configurer l’ID de l’appelant à l’aide de la Skype pour le panneau de configuration serveur Business.'
ms.openlocfilehash: 69d5a1d8f04900933b5de4ebd795961d8b450ca7
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373586"
---
# <a name="create-or-modify-a-translation-rule-for-caller-id-presentation-in-skype-for-business-server"></a><span data-ttu-id="98de5-103">Créer ou modifier une règle de traduction pour la présentation des ID de l’appelant dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="98de5-103">Create or modify a translation rule for caller ID presentation in Skype for Business Server</span></span>

<span data-ttu-id="98de5-104">**Résumé :** Découvrez comment configurer l’ID de l’appelant à l’aide de la Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="98de5-104">**Summary:** Learn how to configure Caller ID by using the Skype for Business Server Control Panel.</span></span>

<span data-ttu-id="98de5-105">Avec Skype pour Business Server, le numéro de téléphone de la personne appelée (autrement dit, le numéro de téléphone appelé) pouvant être traduits du format E.164 au format de numérotation local qui est requis par l' _homologue de jonction_ (c'est-à-dire, la passerelle associée, private branch exchange ( PBX), ou une jonction SIP).</span><span class="sxs-lookup"><span data-stu-id="98de5-105">With Skype for Business Server, the called party's phone number (that is, the phone number called) can be translated from E.164 format to the local dialing format that is required by the  _trunk peer_ (that is, the associated gateway, private branch exchange (PBX), or SIP trunk).</span></span> <span data-ttu-id="98de5-106">À cet effet, vous devez définir une ou plusieurs règles de traduction pour convertir l’URI de demande avant de l’acheminer vers l’homologue de jonction.</span><span class="sxs-lookup"><span data-stu-id="98de5-106">To do this, you must define one or more translation rules to translate the Request URI before routing it to the trunk peer.</span></span>

<span data-ttu-id="98de5-107">Skype pour Business Server également vous offre la possibilité pour traduire également le numéro de téléphone de l’appelant (autrement dit, le numéro de téléphone qui appelle à partir de l’appelant) du format E.164 au format de numérotation local qui est requis par l’homologue de jonction.</span><span class="sxs-lookup"><span data-stu-id="98de5-107">Skype for Business Server also gives you the option to also translate the calling party's phone number (that is, the phone number that the caller is calling from) from E.164 format to the local dialing format that is required by the trunk peer.</span></span> <span data-ttu-id="98de5-108">Par exemple, vous pouvez écrire une règle de conversion pour supprimer +44 au début d’une chaîne de numérotation et utiliser 0144 à la place.</span><span class="sxs-lookup"><span data-stu-id="98de5-108">For example, you can write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>

### <a name="to-configure-caller-id-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="98de5-109">Pour configurer l’ID de l’appelant à l’aide de Skype pour Business Server Control Panel</span><span class="sxs-lookup"><span data-stu-id="98de5-109">To configure Caller ID by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="98de5-110">Ouvrez le panneau de configuration serveur Business Skype.</span><span class="sxs-lookup"><span data-stu-id="98de5-110">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="98de5-111">Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Configuration de la jonction**.</span><span class="sxs-lookup"><span data-stu-id="98de5-111">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

3. <span data-ttu-id="98de5-112">Dans la page **Configuration de la jonction**, double-cliquez sur une jonction existante (par exemple, la jonction **Global**) pour afficher la boîte de dialogue **Modifier la configuration de la jonction**.</span><span class="sxs-lookup"><span data-stu-id="98de5-112">On the **Trunk Configuration** page, double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>

4. <span data-ttu-id="98de5-113">Pour configurer la présentation de l’identification de l’appelant :</span><span class="sxs-lookup"><span data-stu-id="98de5-113">To configure caller ID presentation:</span></span>

   - <span data-ttu-id="98de5-114">Pour choisir une ou plusieurs règles à partir d’une liste de toutes les règles de traduction disponibles dans votre déploiement d’Enterprise Voice, cliquez sur **Sélectionner**.</span><span class="sxs-lookup"><span data-stu-id="98de5-114">To choose one or more rules from a list of all translation rules available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="98de5-115">Dans **Règles de conversion du numéro d’appel**, cliquez sur les règles que vous voulez associer à la jonction, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="98de5-115">In **Calling number translation rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>

   - <span data-ttu-id="98de5-116">Pour définir une nouvelle règle de conversion et l’associer à la jonction, cliquez sur **Nouvelle**.</span><span class="sxs-lookup"><span data-stu-id="98de5-116">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="98de5-117">Pour plus d’informations sur la définition d’une nouvelle règle, voir [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="98de5-117">For details about defining a new rule, see  [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) in the Deployment documentation.</span></span>

   - <span data-ttu-id="98de5-118">Pour modifier une règle de conversion déjà associée à la jonction, cliquez sur le nom de la règle, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="98de5-118">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="98de5-119">Pour plus d’informations, voir [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="98de5-119">For details, see [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) in the Deployment documentation.</span></span>

   - <span data-ttu-id="98de5-120">Pour copier une règle de conversion existante à utiliser comme point de départ pour définir une nouvelle règle, sélectionnez le nom de la règle, cliquez sur **Copier**, puis sur **Coller**.</span><span class="sxs-lookup"><span data-stu-id="98de5-120">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="98de5-121">Pour plus d’informations, voir [Définition des règles de traduction](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx).</span><span class="sxs-lookup"><span data-stu-id="98de5-121">For details, see [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx).</span></span>

   - <span data-ttu-id="98de5-122">Pour supprimer une règle de conversion de la jonction, sélectionnez le nom de la règle et cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="98de5-122">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>

     > [!CAUTION]
     > <span data-ttu-id="98de5-123">N’associez pas de règles de conversion à une configuration de jonction si vous avez configuré les règles de conversion sur l’homologue de jonction associé, car les deux règles risquent d’entrer en conflit.</span><span class="sxs-lookup"><span data-stu-id="98de5-123">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>


