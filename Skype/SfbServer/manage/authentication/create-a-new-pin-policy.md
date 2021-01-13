---
title: Créer une stratégie de code confidentiel dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 8bdf0478-fe9f-4371-93ff-db39381a25db
description: 'Résumé : Créez une stratégie de code confidentiel dans Skype Entreprise Server.'
ms.openlocfilehash: b0d1be74e509fbaddfc59250f4f5ce05a2021260
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828404"
---
# <a name="create-a-new-pin-policy-in-skype-for-business-server"></a><span data-ttu-id="f06fe-103">Créer une stratégie de code confidentiel dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="f06fe-103">Create a new PIN policy in Skype for Business Server</span></span>
 
<span data-ttu-id="f06fe-104">**Résumé :** Créez une stratégie de code confidentiel dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="f06fe-104">**Summary:** Create a new PIN policy in Skype for Business Server.</span></span>
  
<span data-ttu-id="f06fe-105">Vous pouvez utiliser la **page** Stratégie de code confidentiel pour fournir une authentification par code confidentiel aux utilisateurs qui se connectent à Skype Entreprise avec des téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="f06fe-105">You can use the **PIN Policy** page to provide personal identification number (PIN) authentication to users who are connecting to Skype for Business with IP Phones.</span></span> <span data-ttu-id="f06fe-106">Pour utiliser l’authentification par code confidentiel, assurez-vous que l’option **Activer l’authentification par code confidentiel** est sélectionnée dans les paramètres du service web.</span><span class="sxs-lookup"><span data-stu-id="f06fe-106">To use PIN authentication, make sure that **Enable PIN Authentication** is selected in Web Service settings.</span></span>
  
<span data-ttu-id="f06fe-107">Suivez cette procédure pour créer une stratégie de code confidentiel au niveau utilisateur ou site.</span><span class="sxs-lookup"><span data-stu-id="f06fe-107">Follow these steps to create a user-level or a site-level PIN policy.</span></span> 
  
### <a name="to-create-a-user-or-site-pin-policy"></a><span data-ttu-id="f06fe-108">Pour créer une stratégie de code confidentiel au niveau utilisateur ou site</span><span class="sxs-lookup"><span data-stu-id="f06fe-108">To create a user or site PIN policy</span></span>

1.  <span data-ttu-id="f06fe-109">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou qui dispose de droits d’utilisateur équivalents) ou affecté au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à tout ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="f06fe-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="f06fe-110">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="f06fe-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="f06fe-111">Dans la barre de navigation de gauche, cliquez sur **Sécurité**, puis sur **Stratégie de code confidentiel**.</span><span class="sxs-lookup"><span data-stu-id="f06fe-111">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="f06fe-112">Dans la page **Stratégie de code confidentiel**, cliquez sur **Nouveau**, puis effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="f06fe-112">On the **PIN Policy** page, click **New**, and then do one of the following:</span></span>
    
   - <span data-ttu-id="f06fe-p102">Pour créer une stratégie au niveau utilisateur, cliquez sur **Stratégie de l’utilisateur**. Dans **Nouvelle stratégie de code confidentiel**, dans **Nom**, tapez un nom décrivant la stratégie.</span><span class="sxs-lookup"><span data-stu-id="f06fe-p102">To create a user-level policy, click **User policy**. In **New PIN Policy**, in **Name**, type a name that describes the policy.</span></span>
    
   - <span data-ttu-id="f06fe-p103">Pour créer une stratégie au niveau site, cliquez sur **Stratégie du site**. Dans la zone de recherche **Sélectionner un site**, tapez entièrement ou partiellement le nom du site pour lequel vous voulez créer une stratégie. Dans la liste des sites obtenus, cliquez sur le site voulu, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f06fe-p103">To create a site-level policy, click **Site policy**. In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy. In the resulting list of sites, click the site you want, and then click **OK**.</span></span>
    
5. <span data-ttu-id="f06fe-118">Dans le champ **Description**, tapez la description de la stratégie de code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="f06fe-118">In the **Description** field, type a description of the PIN policy.</span></span>
    
6. <span data-ttu-id="f06fe-p104">Dans le champ **Longueur minimale du code confidentiel**, tapez ou sélectionnez la longueur minimale du code confidentiel que vous souhaitez autoriser. La longueur minimale par défaut est de cinq chiffres.</span><span class="sxs-lookup"><span data-stu-id="f06fe-p104">In the **Minimum PIN length** field, type or select the minimum PIN length that you want to allow. The default minimum length is five digits.</span></span>
    
7. <span data-ttu-id="f06fe-p105">Si vous voulez spécifier le nombre maximal de tentatives de connexion avant le verrouillage de l’utilisateur, activez la case à cocher **Spécifier le nombre maximal de tentatives de connexion**. Si vous ne sélectionnez pas cette option, le nombre maximal de tentatives est automatiquement déterminé en fonction de la longueur du code confidentiel. Par défaut, le nombre maximal de tentatives est automatiquement déterminé.</span><span class="sxs-lookup"><span data-stu-id="f06fe-p105">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box. If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length. By default, the maximum number of attempts is automatically determined.</span></span>
    
8. <span data-ttu-id="f06fe-124">Si vous avez activé la case à cocher **Spécifier le nombre maximal de tentatives de connexion**, dans **Nombre maximal de tentatives de connexion**, tapez ou sélectionnez le nombre maximal de tentatives de connexion que vous souhaitez autoriser.</span><span class="sxs-lookup"><span data-stu-id="f06fe-124">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>
    
9. <span data-ttu-id="f06fe-p106">Si vous voulez que les codes confidentiels expirent, activez la case à cocher **Activer l’expiration du code confidentiel**. Si vous ne sélectionnez pas cette option, les codes confidentiels n’expirent jamais. Par défaut, les codes confidentiels n’expirent jamais.</span><span class="sxs-lookup"><span data-stu-id="f06fe-p106">To have PINs expire, select the **Enable PIN expiration** check box. If you do not select this option, PINs will never expire. By default, PINs never expire.</span></span>
    
10. <span data-ttu-id="f06fe-128">Si vous avez activé la case à cocher **Activer l’expiration du code confidentiel**, dans **Le code confidentiel expire au bout de (jours)**, tapez ou sélectionnez le nombre de jours après lequel les codes confidentiels expirent.</span><span class="sxs-lookup"><span data-stu-id="f06fe-128">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>
    
11. <span data-ttu-id="f06fe-p107">Dans **Comptage de l’historique du code confidentiel**, tapez le nombre de codes confidentiels qu’un utilisateur doit créer avant qu’il ne puisse réutiliser un code. Par défaut, les utilisateurs peuvent réutiliser leur code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="f06fe-p107">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN. By default, users can reuse their PINs.</span></span>
    
12. <span data-ttu-id="f06fe-131">Pour autoriser les modèles courants de chiffres dans les codex pin, tels que « 1234 » et « 8888 », cochez la case Autoriser les **modèles courants.**</span><span class="sxs-lookup"><span data-stu-id="f06fe-131">To allow common patterns of digits in PINs, such as "1234" and "8888", select the **Allow common patterns** check box.</span></span> <span data-ttu-id="f06fe-132">Si vous ne sélectionnez pas cette option, seuls les modèles complexes de chiffres sont autorisés.</span><span class="sxs-lookup"><span data-stu-id="f06fe-132">If you do not select this option, only complex patterns of digits are allowed.</span></span> <span data-ttu-id="f06fe-133">Par défaut, seuls les modèles complexes de chiffres sont autorisés.</span><span class="sxs-lookup"><span data-stu-id="f06fe-133">By default, only complex patterns of digits are allowed.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="f06fe-134">Nous vous recommandons de ne pas autoriser les modèles courants.</span><span class="sxs-lookup"><span data-stu-id="f06fe-134">We recommend that you do not allow common patterns.</span></span> 
  
13. <span data-ttu-id="f06fe-135">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="f06fe-135">Click **Commit**.</span></span>
    

