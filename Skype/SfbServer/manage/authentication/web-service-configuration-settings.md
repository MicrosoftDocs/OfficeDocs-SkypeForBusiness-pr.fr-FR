---
title: Gérer les paramètres de configuration des services Web dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f3f04d81-8a1f-427f-bd0f-fb659024e096
description: 'Résumé: gérez les paramètres de configuration des services Web dans Skype entreprise Server.'
ms.openlocfilehash: b2a7f287c9386c89d132e03e96aa25e9472f7008
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297574"
---
# <a name="manage-web-service-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="34fec-103">Gérer les paramètres de configuration des services Web dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="34fec-103">Manage Web Service configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="34fec-104">**Résumé:** Gérer les paramètres de configuration des services Web dans Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="34fec-104">**Summary:** Manage Web Service configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="34fec-105">Vous pouvez utiliser la page de **service Web** pour configurer les méthodes d’authentification pour l’accès à Skype entreprise Server et aux services Web.</span><span class="sxs-lookup"><span data-stu-id="34fec-105">You can use the **Web Service** page to configure the authentication methods for accessing Skype for Business Server related web servers and Web Services.</span></span>
  
<span data-ttu-id="34fec-106">Pour créer une stratégie de service web, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="34fec-106">Follow these steps to create a new Web Service policy.</span></span>
  
### <a name="to-create-new-web-service-configuration-settings"></a><span data-ttu-id="34fec-107">Pour créer des paramètres de configuration d’un service web</span><span class="sxs-lookup"><span data-stu-id="34fec-107">To create new web service configuration settings</span></span>

1.  <span data-ttu-id="34fec-108">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à n’importe quel ordinateur se trouve sur le réseau sur lequel vous avez déployé Skype entreprise Server. .</span><span class="sxs-lookup"><span data-stu-id="34fec-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="34fec-109">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="34fec-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="34fec-110">Dans la barre de navigation de gauche, cliquez sur **Sécurité**, puis sur **Service web**.</span><span class="sxs-lookup"><span data-stu-id="34fec-110">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>
    
4. <span data-ttu-id="34fec-111">Dans la page **Service web**, cliquez sur **Nouveau**, puis effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="34fec-111">On the **Web Service** page, click **New**, and then do one of the following:</span></span>
    
   - <span data-ttu-id="34fec-p101">Pour configurer le service web pour un site, cliquez sur **Configuration du site**. Dans **Sélectionner un site**, cliquez sur le site auquel le service web s’appliquera, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="34fec-p101">To configure the Web Service for a site, click **Site configuration**. In **Select a Site**, click the site to which the Web Service policy will be applied a site and click **OK**.</span></span>
    
   - <span data-ttu-id="34fec-p102">Pour configurer le service web pour un pool, cliquez sur **Configuration du pool**. Dans **Sélectionner un service**, cliquez sur le service auquel la stratégie de service web s’appliquera, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="34fec-p102">To configure the Web Service for a pool, click **Pool configuration**. In **Select a Service**, click the service to which the Web Service policy will be applied and click **OK**.</span></span> 
    
5. <span data-ttu-id="34fec-116">Dans **Nouveau paramètre de service web**, dans **Authentification Windows intégrée**, sélectionnez **Négocier**, **Authentification Windows intégrée** ou **Aucun**.</span><span class="sxs-lookup"><span data-stu-id="34fec-116">In **New Web Service Setting**, in **Integrated Windows authentication**, select **Negotiate**, **Integrated Windows authentication**, or **None**.</span></span>
    
6. <span data-ttu-id="34fec-117">Sélectionnez une ou plusieurs des options ci-dessous en fonction des capacités des clients et de la prise en charge dans votre environnement :</span><span class="sxs-lookup"><span data-stu-id="34fec-117">Select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="34fec-118">**Activer l’authentification par code confidentiel** pour pouvoir authentifier les clients au moyen de codes confidentiels.</span><span class="sxs-lookup"><span data-stu-id="34fec-118">**Enable PIN Authentication** to enable clients to be authenticated using PIN numbers.</span></span>
    
   - <span data-ttu-id="34fec-119">**Activer l’authentification par certificat** pour que les serveurs du pool émettent des certificats pour les clients.</span><span class="sxs-lookup"><span data-stu-id="34fec-119">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
   - <span data-ttu-id="34fec-120">**Activer le téléchargement de chaîne de certificats** pour que les serveurs présentés avec un certificat d’authentification téléchargent la chaîne de certificats du certificat concerné.</span><span class="sxs-lookup"><span data-stu-id="34fec-120">**Enable certificate chain download** to have servers presented with an authentication certificate download the certificate chain for that certificate.</span></span>
    
7. <span data-ttu-id="34fec-121">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="34fec-121">Click **Commit**.</span></span>
    
## <a name="modify-existing-web-service-configuration-settings"></a><span data-ttu-id="34fec-122">Modification des paramètres de configuration d’un service web existant</span><span class="sxs-lookup"><span data-stu-id="34fec-122">Modify existing Web Service configuration settings</span></span>

<span data-ttu-id="34fec-123">Vous pouvez utiliser la page de **service Web** pour configurer les méthodes d’authentification pour l’accès à Skype entreprise Server et aux services Web.</span><span class="sxs-lookup"><span data-stu-id="34fec-123">You can use the **Web Service** page to configure the authentication methods for accessing Skype for Business Server related web servers and Web Services.</span></span>
  
<span data-ttu-id="34fec-124">Pour modifier une stratégie de service web existante, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="34fec-124">Follow these steps to modify an existing Web Service policy.</span></span>
  
### <a name="to-modify-existing-web-service-configuration-settings"></a><span data-ttu-id="34fec-125">Pour modifier des paramètres de configuration d’un service web existant</span><span class="sxs-lookup"><span data-stu-id="34fec-125">To modify existing Web service configuration settings</span></span>

1.  <span data-ttu-id="34fec-126">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à n’importe quel ordinateur se trouve sur le réseau sur lequel vous avez déployé Skype entreprise Server. .</span><span class="sxs-lookup"><span data-stu-id="34fec-126">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="34fec-127">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="34fec-127">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="34fec-128">Dans la barre de navigation de gauche, cliquez sur **Sécurité**, puis sur **Service web**.</span><span class="sxs-lookup"><span data-stu-id="34fec-128">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>
    
4. <span data-ttu-id="34fec-129">Dans la page **Service web**, sélectionnez une configuration, cliquez sur le menu **Edition**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="34fec-129">On the **Web Service** page, click a configuration, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="34fec-130">Dans **Modifier le paramètre de service web**, sous **Authentification Windows intégrée**, sélectionnez **Négocier**, **Authentification Windows intégrée** ou **Aucune**.</span><span class="sxs-lookup"><span data-stu-id="34fec-130">In **Edit Web Service Setting**, in **Integrated Windows authentication**, select **Negotiate**, **Integrated Windows authentication**, or **None**.</span></span>
    
6. <span data-ttu-id="34fec-131">Sélectionnez une ou plusieurs des options ci-dessous en fonction des capacités des clients et de la prise en charge dans votre environnement :</span><span class="sxs-lookup"><span data-stu-id="34fec-131">Select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="34fec-132">**Activer l’authentification par code confidentiel** pour pouvoir authentifier les clients au moyen de codes confidentiels.</span><span class="sxs-lookup"><span data-stu-id="34fec-132">**Enable PIN Authentication** to enable clients to be authenticated using PIN numbers.</span></span>
    
   - <span data-ttu-id="34fec-133">**Activer l’authentification par certificat** pour que les serveurs du pool émettent des certificats pour les clients.</span><span class="sxs-lookup"><span data-stu-id="34fec-133">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
   - <span data-ttu-id="34fec-134">**Activer le téléchargement de chaîne de certificats** pour que les serveurs présentés avec un certificat d’authentification téléchargent la chaîne de certificats du certificat concerné.</span><span class="sxs-lookup"><span data-stu-id="34fec-134">**Enable certificate chain download** to have servers presented with an authentication certificate download the certificate chain for that certificate.</span></span>
    
7. <span data-ttu-id="34fec-135">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="34fec-135">Click **Commit**.</span></span>
    
## <a name="delete-existing-web-service-configuration-settings"></a><span data-ttu-id="34fec-136">Suppression des paramètres de configuration d’un service web existant</span><span class="sxs-lookup"><span data-stu-id="34fec-136">Delete existing Web Service configuration settings</span></span>

<span data-ttu-id="34fec-137">Pour supprimer les paramètres de configuration des services web, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="34fec-137">Follow these steps to delete web service configuration settings.</span></span>
  
### <a name="to-delete-web-service-configuration-settings"></a><span data-ttu-id="34fec-138">Pour supprimer des paramètres de configuration d’un service web existant</span><span class="sxs-lookup"><span data-stu-id="34fec-138">To delete web service configuration settings</span></span>

1.  <span data-ttu-id="34fec-139">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à n’importe quel ordinateur se trouve sur le réseau sur lequel vous avez déployé Skype entreprise Server. .</span><span class="sxs-lookup"><span data-stu-id="34fec-139">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="34fec-140">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="34fec-140">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="34fec-141">Dans la barre de navigation de gauche, cliquez sur **Sécurité**, puis sur **Service web**.</span><span class="sxs-lookup"><span data-stu-id="34fec-141">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>
    
4. <span data-ttu-id="34fec-142">Dans le champ de recherche de la page **Service web**, tapez l’intégralité ou une partie du nom de la stratégie à supprimer.</span><span class="sxs-lookup"><span data-stu-id="34fec-142">On the **Web Service** page, and in the search field, type all or part of the name of the policy you want to delete.</span></span>
    
5. <span data-ttu-id="34fec-143">Dans la liste des stratégies, cliquez sur la stratégie à supprimer, sur **Modifier**, puis sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="34fec-143">In the list of policies, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="34fec-144">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="34fec-144">Click **OK**.</span></span>
    
## <a name="deleting-web-service-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="34fec-145">Supprimer des paramètres de configuration de service Web à l’aide des applets de cmdlet Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="34fec-145">Deleting Web Service Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="34fec-146">Vous pouvez supprimer des paramètres de configuration de service Web à l’aide de Windows PowerShell et de l’applet de passe **Remove-CsWebServiceConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="34fec-146">You can delete web service configuration settings by using Windows PowerShell and the **Remove-CsWebServiceConfiguration** cmdlet.</span></span> <span data-ttu-id="34fec-147">Vous pouvez exécuter cette applet de commande dans Skype entreprise Server Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="34fec-147">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="34fec-148">Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Skype entreprise Server, voir l’article sur le blog [«démarrage rapide: gestion de Microsoft Lync Server 2010 à l’aide de Remote PowerShell»](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="34fec-148">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="34fec-149">Le processus est le même dans Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="34fec-149">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-delete-a-specific-collection-of-web-service-configuration-settings"></a><span data-ttu-id="34fec-150">Pour supprimer une collection de paramètres de configuration des services web</span><span class="sxs-lookup"><span data-stu-id="34fec-150">To delete a specific collection of web service configuration settings</span></span>

- <span data-ttu-id="34fec-151">La commande ci-dessous supprime les paramètres de sécurité des services web appliqués au site de Redmond :</span><span class="sxs-lookup"><span data-stu-id="34fec-151">The following command removes the Web Service security settings applied to the Redmond site:</span></span>
    
  ```
  Remove-CsWebServiceConfiguration -Identity "site:Redmond"
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="34fec-152">Pour supprimer tous les paramètres de configuration des services web appliqués à l’étendue du site</span><span class="sxs-lookup"><span data-stu-id="34fec-152">To delete all of the web service configuration settings applied to the site scope</span></span>

<span data-ttu-id="34fec-153">La commande ci-dessous supprime tous les paramètres de sécurité des services web appliqués à l’étendue des services :</span><span class="sxs-lookup"><span data-stu-id="34fec-153">The following command removes all of the Web Service security settings applied to the service scope:</span></span>
    
  ```
  Get-CsWebServiceConfiguration -Filter "service:*" | Remove-CsWebServiceConfiguration
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-that-allow-certificate-authentication"></a><span data-ttu-id="34fec-154">Pour supprimer tous les paramètres de configuration des services web qui autorisent l’authentification des certificats</span><span class="sxs-lookup"><span data-stu-id="34fec-154">To delete all of the web service configuration settings that allow certificate authentication</span></span>

<span data-ttu-id="34fec-155">La commande ci-dessous supprime tous les paramètres de sécurité des services web qui autorisent l’authentification des certificats :</span><span class="sxs-lookup"><span data-stu-id="34fec-155">The following command removes all the Web Service security settings that allow the use of certificate authentication:</span></span>
    
  ```
  Get-CsWebServiceConfiguration | Where-Object {$_.UseCertificateAuth -eq $True} | Remove-CsWebServiceConfiguration
  ```

<span data-ttu-id="34fec-156">Pour plus d’informations, consultez la rubrique [Remove-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cswebserviceconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="34fec-156">For details, see [Remove-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cswebserviceconfiguration?view=skype-ps).</span></span>
  

