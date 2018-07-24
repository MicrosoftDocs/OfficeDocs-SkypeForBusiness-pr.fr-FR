---
title: Gérer les paramètres de configuration du serveur d’inscriptions dans Skype pour Business Server
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eddfbdd2-cfd0-4c03-986e-443d6728db7d
description: 'Résumé : Gérer les paramètres de configuration de serveur d’inscriptions de Skype pour Business Server.'
ms.openlocfilehash: 65dfae7e518ef1b561a6782f9555de2d5dd6a6fa
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20998994"
---
# <a name="manage-registrar-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="aabed-103">Gérer les paramètres de configuration du serveur d’inscriptions dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="aabed-103">Manage Registrar configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="aabed-104">**Résumé :** Gérer les paramètres de configuration de serveur d’inscriptions de Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="aabed-104">**Summary:** Manage Registrar configuration settings for Skype for Business Server.</span></span>
  
<span data-ttu-id="aabed-p101">Vous pouvez utiliser le serveur d’inscriptions avancé pour configurer les méthodes d’authentification du serveur proxy. Le protocole d’authentification que vous spécifiez détermine le type de difficultés que les serveurs du pool posent aux clients. Les protocoles disponibles sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="aabed-p101">You can use the Registrar to configure proxy server authentication methods. The authentication protocol you specify determines which type of challenges the servers in the pool issue to clients. The available protocols are:</span></span>
  
- <span data-ttu-id="aabed-108">**Kerberos** C’est le modèle d’authentification par mot de passe le plus puissant aux clients, mais il est généralement disponible uniquement pour les clients d’entreprise, car il exige une connexion client à un centre de Distribution de clés (contrôleur de domaine Kerberos).</span><span class="sxs-lookup"><span data-stu-id="aabed-108">**Kerberos** This is the strongest password-based authentication scheme available to clients, but it is normally available only to enterprise clients because it requires client connection to a Key Distribution Center (Kerberos domain controller).</span></span> <span data-ttu-id="aabed-109">Ce paramètre est adapté si le serveur ne doit authentifier que des clients entreprise.</span><span class="sxs-lookup"><span data-stu-id="aabed-109">This setting is appropriate if the server authenticates only enterprise clients.</span></span>
    
- <span data-ttu-id="aabed-110">**NTLM** Il s’agit de l’authentification par mot de passe pour les clients qui utilisent un schéma de hachage stimulation / réponse au mot de passe.</span><span class="sxs-lookup"><span data-stu-id="aabed-110">**NTLM** This is the password-based authentication available to clients that use a challenge-response hashing scheme on the password.</span></span> <span data-ttu-id="aabed-111">C’est la seule forme d’authentification proposée aux clients ne disposant pas d’une connectivité à un centre de distribution des clés (contrôleur de domaine Kerberos), comme les utilisateurs distants.</span><span class="sxs-lookup"><span data-stu-id="aabed-111">This is the only form of authentication available to clients without connectivity to a Key Distribution Center (Kerberos domain controller), such as remote users.</span></span> <span data-ttu-id="aabed-112">Si un serveur n’authentifie que des utilisateurs distants, vous devez choisir NTLM.</span><span class="sxs-lookup"><span data-stu-id="aabed-112">If a server authenticates only remote users, you should choose NTLM.</span></span>
    
- <span data-ttu-id="aabed-113">**Authentification par certificat** Il s’agit de la méthode d’authentification lorsque le serveur doit obtenir des certificats à partir de clients Lync Phone Edition, les téléphones de partie commune, Skype pour les entreprises et l’application Lync Windows Store.</span><span class="sxs-lookup"><span data-stu-id="aabed-113">**Certificate authentication** This is the new authentication method when the server needs to obtain certificates from Lync Phone Edition clients, common area phones, Skype for Business and the Lync Windows Store app.</span></span> <span data-ttu-id="aabed-114">Sur les clients Lync Phone Edition, après un utilisateur se connecte et est authentifié avec succès en fournissant un code confidentiel (PIN), Skype pour Business Server, puis met en service l’URI SIP sur le téléphone et met en service un Skype pour Business Server connecté certificat ou un certificat utilisateur qui identifie Joe (Ex : SN=joe@contoso.com) sur le téléphone.</span><span class="sxs-lookup"><span data-stu-id="aabed-114">On Lync Phone Edition clients, after a user signs in and is successfully authenticated by providing a personal identification number (PIN), Skype for Business Server then provisions the SIP URI to the phone and provisions a Skype for Business Server signed certificate or a user certificate that identifies Joe (Ex: SN=joe@contoso.com ) to the phone.</span></span> <span data-ttu-id="aabed-115">Ce certificat est utilisé pour l’authentification auprès du serveur d’inscriptions et des Services Web.</span><span class="sxs-lookup"><span data-stu-id="aabed-115">This certificate is used for authenticating with the Registrar and Web Services.</span></span>
    
> [!NOTE]
> <span data-ttu-id="aabed-p105">Nous vous recommandons d’activer Kerberos et NTLM lorsqu’un serveur prend en charge l’authentification des clients distants et d’entreprise. Le serveur Edge et les serveurs internes communiquent pour veiller à ce qu’une authentification NTLM seulement soit proposée aux clients distants. Si seul Kerberos est activé sur ces serveurs, ils ne peuvent pas authentifier les utilisateurs distants. Si des utilisateurs d’entreprise s’authentifient également sur le serveur, Kerberos est utilisé.</span><span class="sxs-lookup"><span data-stu-id="aabed-p105">We recommend that you enable both Kerberos and NTLM when a server supports authentication for both remote and enterprise clients. The Edge Server and internal servers communicate to ensure that only NTLM authentication is offered to remote clients. If only Kerberos is enabled on these servers, they cannot authenticate remote users. If enterprise users also authenticate against the server, Kerberos is used.</span></span> 
  
<span data-ttu-id="aabed-120">Si vous utilisez les clients d’application Lync Windows Store, vous devez activer l’authentification par certificat.</span><span class="sxs-lookup"><span data-stu-id="aabed-120">If you will use Lync Windows Store app clients, you must enable certificate authentication.</span></span>
  
### <a name="to-create-new-registrar-configuration-settings"></a><span data-ttu-id="aabed-121">Pour créer des paramètres de configuration du serveur d’inscriptions avancé</span><span class="sxs-lookup"><span data-stu-id="aabed-121">To create new Registrar configuration settings</span></span>

1.  <span data-ttu-id="aabed-122">À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur n’importe quel ordinateur qui se trouve dans le réseau dans lequel vous avez déployé Skype pour Business Server .</span><span class="sxs-lookup"><span data-stu-id="aabed-122">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="aabed-123">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="aabed-123">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="aabed-124">Dans la barre de navigation de gauche, cliquez sur **Sécurité**, puis sur **Serveur d’inscriptions avancé**.</span><span class="sxs-lookup"><span data-stu-id="aabed-124">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>
    
4. <span data-ttu-id="aabed-125">Dans la page **Serveur d’inscriptions avancé**, cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="aabed-125">On the **Registrar** page, click **New**</span></span>
    
5. <span data-ttu-id="aabed-126">Dans **Sélectionner un service**, cliquez sur le service auquel le serveur d’inscriptions avancé s’appliquera, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="aabed-126">In **Select a Service**, click the service to which the Registrar is to be applied and then click **OK**.</span></span>
    
6. <span data-ttu-id="aabed-127">Dans **Nouveau paramètre de serveur d’inscriptions avancé**, sélectionnez un ou plusieurs des éléments ci-dessous selon les fonctionnalités des clients et la prise en charge de votre environnement :</span><span class="sxs-lookup"><span data-stu-id="aabed-127">In **New Registrar Setting**, select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="aabed-128">**Activer l’authentification Kerberos** pour que les serveurs du pool émettent des demandes à l’aide de l’authentification Kerberos.</span><span class="sxs-lookup"><span data-stu-id="aabed-128">**Enable Kerberos authentication** to have the servers in the pool issue challenges using Kerberos authentication.</span></span>
    
   - <span data-ttu-id="aabed-129">**Activer l’authentification NTLM** pour que les serveurs du pool émettent des demandes à l’aide de l’authentification NTLM.</span><span class="sxs-lookup"><span data-stu-id="aabed-129">**Enable NTLM authentication** to have the servers in the pool issue challenges using NTLM.</span></span>
    
   - <span data-ttu-id="aabed-130">**Activer l’authentification par certificat** pour que les serveurs du pool émettent des certificats pour les clients.</span><span class="sxs-lookup"><span data-stu-id="aabed-130">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
7. <span data-ttu-id="aabed-131">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="aabed-131">Click **Commit**.</span></span>
    
## <a name="modify-existing-registrar-configuration-settings"></a><span data-ttu-id="aabed-132">Modification des paramètres de configuration d’un serveur d’inscriptions avancé existant</span><span class="sxs-lookup"><span data-stu-id="aabed-132">Modify existing Registrar configuration settings</span></span>

<span data-ttu-id="aabed-133">Vous pouvez utiliser le serveur d’inscriptions avancé pour configurer les protocoles d’authentification du serveur proxy.</span><span class="sxs-lookup"><span data-stu-id="aabed-133">You can use the Registrar to configure proxy server authentication protocols.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="aabed-p106">Nous vous recommandons d’activer Kerberos et NTLM lorsqu’un serveur prend en charge l’authentification des clients distants et d’entreprise. Le serveur Edge et les serveurs internes communiquent pour veiller à ce qu’une authentification NTLM seulement soit proposée aux clients distants. Si seul Kerberos est activé sur ces serveurs, ils ne peuvent pas authentifier les utilisateurs distants. Si des utilisateurs d’entreprise s’authentifient également sur le serveur, Kerberos est utilisé.</span><span class="sxs-lookup"><span data-stu-id="aabed-p106">We recommend that you enable both Kerberos and NTLM when a server supports authentication for both remote and enterprise clients. The Edge Server and internal servers communicate to ensure that only NTLM authentication is offered to remote clients. If only Kerberos is enabled on these servers, they cannot authenticate remote users. If enterprise users also authenticate against the server, Kerberos is used.</span></span> 
  
<span data-ttu-id="aabed-138">Pour modifier un serveur d’inscriptions avancé, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="aabed-138">Follow these steps to modify an existing Registrar.</span></span> 
  
### <a name="to-modify-existing-registrar-configuration-settings"></a><span data-ttu-id="aabed-139">Pour modifier des paramètres de configuration d’un serveur d’inscriptions avancé existant</span><span class="sxs-lookup"><span data-stu-id="aabed-139">To modify existing registrar configuration settings</span></span>

1.  <span data-ttu-id="aabed-140">À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur n’importe quel ordinateur qui se trouve dans le réseau dans lequel vous avez déployé Skype pour Business Server .</span><span class="sxs-lookup"><span data-stu-id="aabed-140">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="aabed-141">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="aabed-141">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="aabed-142">Dans la barre de navigation de gauche, cliquez sur **Sécurité**, puis sur **Serveur d’inscriptions avancé**.</span><span class="sxs-lookup"><span data-stu-id="aabed-142">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>
    
4. <span data-ttu-id="aabed-143">Dans la page **Serveur d’inscriptions avancé**, sélectionnez un service, cliquez sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="aabed-143">On the **Registrar** page, click a service, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="aabed-144">Dans **Modifier le paramètre du serveur d’inscriptions avancé**, sélectionnez un ou plusieurs des éléments ci-dessous selon les fonctionnalités des clients et la prise en charge de votre environnement :</span><span class="sxs-lookup"><span data-stu-id="aabed-144">In **Edit Registrar Setting**, select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="aabed-145">**Activer l’authentification Kerberos** pour que les serveurs du pool émettent des demandes à l’aide de l’authentification Kerberos.</span><span class="sxs-lookup"><span data-stu-id="aabed-145">**Enable Kerberos authentication** to have the servers in the pool issue challenges using Kerberos authentication.</span></span>
    
   - <span data-ttu-id="aabed-146">**Activer l’authentification NTLM** pour que les serveurs du pool émettent des demandes à l’aide de l’authentification NTLM.</span><span class="sxs-lookup"><span data-stu-id="aabed-146">**Enable NTLM authentication** to have the servers in the pool issue challenges using NTLM.</span></span>
    
   - <span data-ttu-id="aabed-147">**Activer l’authentification par certificat** pour que les serveurs du pool émettent des certificats pour les clients.</span><span class="sxs-lookup"><span data-stu-id="aabed-147">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
6. <span data-ttu-id="aabed-148">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="aabed-148">Click **Commit**.</span></span>
    
### <a name="to-delete-registrar-configuration-settings"></a><span data-ttu-id="aabed-149">Pour supprimer des paramètres de configuration du serveur d’inscriptions avancé</span><span class="sxs-lookup"><span data-stu-id="aabed-149">To delete Registrar configuration settings</span></span>

1. <span data-ttu-id="aabed-150">À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur n’importe quel ordinateur qui se trouve dans le réseau dans lequel vous avez déployé Skype pour Business Server .</span><span class="sxs-lookup"><span data-stu-id="aabed-150">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="aabed-151">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="aabed-151">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="aabed-152">Dans la barre de navigation de gauche, cliquez sur **Sécurité**, puis sur **Serveur d’inscriptions avancé**.</span><span class="sxs-lookup"><span data-stu-id="aabed-152">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>
    
4. <span data-ttu-id="aabed-153">Dans la page **Serveur d’inscriptions avancé**, dans le champ de recherche, tapez entièrement ou partiellement le nom du serveur d’inscriptions avancé à supprimer.</span><span class="sxs-lookup"><span data-stu-id="aabed-153">On the **Registrar** page, and in the search field, type all or part of the name of the Registrar you want to delete.</span></span>
    
5. <span data-ttu-id="aabed-154">Dans la liste, sélectionnez le serveur d’inscriptions avancé souhaité, cliquez sur **Modifier**, puis sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="aabed-154">In the list, click the Registrar that you want, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="aabed-155">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="aabed-155">Click **OK**.</span></span>
    
## <a name="removing-registrar-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="aabed-156">Suppression des paramètres de Configuration du serveur d’inscriptions à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="aabed-156">Removing Registrar Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="aabed-157">Vous pouvez supprimer les paramètres de configuration du serveur d’inscriptions à l’aide de Windows PowerShell et l’applet de commande **Remove-CsProxyConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="aabed-157">You can delete the Registrar configuration settings by using Windows PowerShell and the **Remove-CsProxyConfiguration** cmdlet.</span></span> <span data-ttu-id="aabed-158">Vous pouvez exécuter cette applet de commande à partir de la Skype pour Business Server Management Shell ou d’une session à distance de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="aabed-158">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="aabed-159">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Skype pour Business Server, consultez l’article de blog [« rapide démarrer : gestion de Microsoft PowerShell Lync Server 2010 à l’aide à distance »](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="aabed-159">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="aabed-160">Le processus est le même dans Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="aabed-160">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-specific-set-of-registrar-security-settings"></a><span data-ttu-id="aabed-161">Pour supprimer un ensemble spécifique de paramètres de sécurité du serveur d’inscriptions avancé</span><span class="sxs-lookup"><span data-stu-id="aabed-161">To remove a specific set of Registrar security settings</span></span>

- <span data-ttu-id="aabed-162">La commande ci-dessous supprime les paramètres de sécurité du serveur d’inscriptions avancé appliqués au serveur Edge atl-edge-011.litwareinc.com :</span><span class="sxs-lookup"><span data-stu-id="aabed-162">The following command removes the Registrar security settings applied to the edge Server atl-edge-011.litwareinc.com:</span></span>
    
  ```
  Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-applied-to-the-site-scope"></a><span data-ttu-id="aabed-163">Pour supprimer tous les paramètres de sécurité du serveur d’inscriptions avancé appliqués à l’étendue Site</span><span class="sxs-lookup"><span data-stu-id="aabed-163">To remove all of the Registrar security settings applied to the site scope</span></span>

- <span data-ttu-id="aabed-164">La commande ci-dessous supprime tous les paramètres de sécurité du serveur d’inscriptions avancé appliqués au service de serveur d’inscriptions avancé :</span><span class="sxs-lookup"><span data-stu-id="aabed-164">The following command removes all the Registrar security settings applied to the Registrar service:</span></span>
    
  ```
  Get-CsProxyConfiguration -Filter "service:Registrar:*" | Remove-CsProxyConfiguration
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-that-allow-ntlm-authentication"></a><span data-ttu-id="aabed-165">Pour supprimer tous les paramètres de sécurité du serveur d’inscriptions avancé qui permettent l’authentification NTLM</span><span class="sxs-lookup"><span data-stu-id="aabed-165">To remove all of the Registrar security settings that allow NTLM authentication</span></span>

- <span data-ttu-id="aabed-166">La commande ci-dessous supprime tous les paramètres de sécurité du serveur d’inscriptions avancé qui permettent l’utilisation de NTLM pour l’authentification client :</span><span class="sxs-lookup"><span data-stu-id="aabed-166">The following command deletes all the Registrar security settings that allow the use of NTLM for client authentication:</span></span>
    
  ```
  Get-CsProxyConfiguration | Where-Object {$_.UseNtlmForClientToProxyAuth -eq $True}| Remove-CsProxyConfiguration
  ```

<span data-ttu-id="aabed-167">Pour plus d’informations, voir [Remove-CsProxyConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csproxyconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="aabed-167">For details, see [Remove-CsProxyConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csproxyconfiguration?view=skype-ps).</span></span>
  

