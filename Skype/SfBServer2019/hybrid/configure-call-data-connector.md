---
title: Configurer le connecteur de données d’appel
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Instructions pour configurer le connecteur de données d’appel, qui permet de télémétrie à partir de Skype pour Business locale pour être affichés à l’aide de Skype pour les outils professionnels en ligne.
ms.openlocfilehash: 959bb182da91029fd43ebc3ccb99fb5a69d820b2
ms.sourcegitcommit: 7d65eafd5b0163ece91deb7801458c7a45fcc4f7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/29/2018
ms.locfileid: "25838822"
---
# <a name="configure-call-data-connector"></a><span data-ttu-id="92eec-103">Configurer le connecteur de données d’appel</span><span class="sxs-lookup"><span data-stu-id="92eec-103">Configure Call Data Connector</span></span>

<span data-ttu-id="92eec-104">Cet article décrit comment configurer le connecteur de données d’appel : un ensemble d’outils unique qui permet l’affichage Skype pour serveur appeler la qualité des données métiers à l’aide de Skype des outils Business Online appeler qualité du tableau de bord (CQD) et appelez Analytique (CA).</span><span class="sxs-lookup"><span data-stu-id="92eec-104">This article describes how to configure Call Data Connector--a single toolset that enables viewing Skype for Business Server Call Quality Data using Skype for Business Online Call Quality Dashboard (CQD) and Call Analytics (CA) tools.</span></span> 

> [!NOTE]
> <span data-ttu-id="92eec-105">Version d’évaluation, tableau de bord Analytique appeler uniquement est disponible.</span><span class="sxs-lookup"><span data-stu-id="92eec-105">At public preview release, only Call Analytics dashboard is available.</span></span>

<span data-ttu-id="92eec-106">Pour plus d’informations sur les avantages de l’appel de connecteur de données et les composants requis, tels que les exigences de rôle et la configuration de la connectivité hybride, voir [Planification de connecteur de données d’appel](plan-call-data-connector.md).</span><span class="sxs-lookup"><span data-stu-id="92eec-106">For more information about Call Data Connector benefits and pre-requisites, such as role requirements and setting up hybrid connectivity, see [Plan Call Data Connector](plan-call-data-connector.md).</span></span>

## <a name="enable-monitoring"></a><span data-ttu-id="92eec-107">Activer la surveillance</span><span class="sxs-lookup"><span data-stu-id="92eec-107">Enable Monitoring</span></span>
 
<span data-ttu-id="92eec-108">Vous devez configurer l’enregistrement de données appels (CDR) et qualité de l’expérience (QoE) collecte des données dans votre serveur frontal du pool surveillance, locales bases de données LCSCdr et QoEMetrics ; dans le cas contraire, les tableaux de bord qualité des appels Analytique appel n’obtenir des données pour fonctionner avec.</span><span class="sxs-lookup"><span data-stu-id="92eec-108">You must configure Call Data Recording (CDR) and Quality of Experience (QoE) data collection in your front end pool Monitoring,with local LCSCdr and QoEMetrics databases; otherwise, the Call Analytics and Call Quality Dashboards won’t get data to work with.</span></span> <span data-ttu-id="92eec-109">Avant que vous configurer appel données connecteur, suivez les étapes fournies dans [Deploy surveillance dans Skype pour Business Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) pour configurer à la fois des détails des appels et QoE ainsi que surveillance de base.</span><span class="sxs-lookup"><span data-stu-id="92eec-109">Before you Configure Call Data Connector, follow the steps provided in [Deploy monitoring in Skype for Business Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) to configure both CDR and QoE as well as basic Monitoring.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="92eec-110">Connecteur de données d’appel ne fonctionne pas si l’analyse n’est pas activé sur le pool frontal.</span><span class="sxs-lookup"><span data-stu-id="92eec-110">Call Data Connector will not function if Monitoring is not enabled on the front end pool.</span></span>

## <a name="enable-call-data-connector"></a><span data-ttu-id="92eec-111">Activer le connecteur de données d’appel</span><span class="sxs-lookup"><span data-stu-id="92eec-111">Enable Call Data Connector</span></span>

<span data-ttu-id="92eec-112">Pour configurer et activer le connecteur de données d’appel, vous allez utiliser les applets de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="92eec-112">To configure and enable Call Data Connector, you will use the following cmdlets:</span></span>

| <span data-ttu-id="92eec-113">Applet de commande</span><span class="sxs-lookup"><span data-stu-id="92eec-113">Cmdlet</span></span>| <span data-ttu-id="92eec-114">Description</span><span class="sxs-lookup"><span data-stu-id="92eec-114">Description</span></span>|
| :-----------------|---------------:|
| <span data-ttu-id="92eec-115">Nouvelle CsCloudCallDataConnection</span><span class="sxs-lookup"><span data-stu-id="92eec-115">New-CsCloudCallDataConnection</span></span> | <span data-ttu-id="92eec-116">Une applet de commande en ligne qui établit un collecteur de données en ligne.</span><span class="sxs-lookup"><span data-stu-id="92eec-116">An online cmdlet that establishes an online data collector.</span></span>|
| <span data-ttu-id="92eec-117">Get-CsCloudCallDataConnection</span><span class="sxs-lookup"><span data-stu-id="92eec-117">Get-CsCloudCallDataConnection</span></span> | <span data-ttu-id="92eec-118">Une applet de commande en ligne qui Récupère un collecteur de données en ligne existant.</span><span class="sxs-lookup"><span data-stu-id="92eec-118">An online cmdlet that retrieves an existing online data collector.</span></span>|  
| <span data-ttu-id="92eec-119">Get-CsCloudCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="92eec-119">Get-CsCloudCallDataConnector</span></span> | <span data-ttu-id="92eec-120">Applet de commande locale qui Récupère les informations de connexion créées par l’applet de commande New-CsCloudCallDataConnection.</span><span class="sxs-lookup"><span data-stu-id="92eec-120">An on-premises cmdlet that retrieves the connection information created by the New-CsCloudCallDataConnection cmdlet.</span></span> |
| <span data-ttu-id="92eec-121">Set-CsCloudCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="92eec-121">Set-CsCloudCallDataConnector</span></span> | <span data-ttu-id="92eec-122">Applet de commande locale qui permet d’enregistrer une copie locale, les informations de connexion créées par l’applet de commande New-CsCloudCallDataConnection.</span><span class="sxs-lookup"><span data-stu-id="92eec-122">An on-premises cmdlet that saves an on-premises copy of the connection information created by the New-CsCloudCallDataConnection cmdlet.</span></span> |  
| <span data-ttu-id="92eec-123">Set-CsCloudCallDataConnectorConfiguration</span><span class="sxs-lookup"><span data-stu-id="92eec-123">Set-CsCloudCallDataConnectorConfiguration</span></span> | <span data-ttu-id="92eec-124">Applet de commande locale qui permet d’activer ou désactiver le connecteur et personnaliser le niveau de l’étendue.</span><span class="sxs-lookup"><span data-stu-id="92eec-124">An on-premises cmdlet that allows you to enable or disable the connector and customize the scope level.</span></span>|

### <a name="configure-your-environment"></a><span data-ttu-id="92eec-125">Configurer votre environnement</span><span class="sxs-lookup"><span data-stu-id="92eec-125">Configure your environment</span></span> 

<span data-ttu-id="92eec-126">Pour configurer votre environnement pour activer un collecteur de données en ligne, vous devez tout d’abord vous connecter à Skype pour Business Online PowerShell en tant qu’administrateur.</span><span class="sxs-lookup"><span data-stu-id="92eec-126">To configure your environment to enable an online data collector, you must first log in to Skype for Business Online PowerShell as an administrator.</span></span> <span data-ttu-id="92eec-127">Pour plus d’informations, voir [Gérer les Skype pour Business en ligne avec Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="92eec-127">For more information, see [Manage Skype for Business Online with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

<span data-ttu-id="92eec-128">Il existe deux méthodes pour la connexion à Skype pour Business Online PowerShell :</span><span class="sxs-lookup"><span data-stu-id="92eec-128">There are two methods for logging in to Skype for Business Online PowerShell:</span></span>

- <span data-ttu-id="92eec-129">À partir de la Skype pour Business Server 2019 management shell (méthode recommandée)</span><span class="sxs-lookup"><span data-stu-id="92eec-129">From the Skype for Business Server 2019 management shell (recommended method)</span></span>
- <span data-ttu-id="92eec-130">À partir d’une autre session PowerShell</span><span class="sxs-lookup"><span data-stu-id="92eec-130">From another PowerShell session</span></span>

#### <a name="log-in-to-skype-for-business-online-powershell-from-the-skype-for-business-server-management-shell-recommended-method"></a><span data-ttu-id="92eec-131">Connectez-vous à Skype pour Business Online PowerShell à partir de la Skype pour Business Server management shell (méthode recommandée)</span><span class="sxs-lookup"><span data-stu-id="92eec-131">Log in to Skype for Business Online PowerShell from the Skype for Business Server management shell (recommended method)</span></span>

1. <span data-ttu-id="92eec-132">Si l’activation du connector pour la première fois, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="92eec-132">If enabling the connector for the first time, run the following command:</span></span>

   ```
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. <span data-ttu-id="92eec-133">Si vous obtenez une erreur la connexion existe déjà, cela signifie que la connexion de données déjà appel existe pour votre client.</span><span class="sxs-lookup"><span data-stu-id="92eec-133">If you get an error that the connection already exists, this means that the call data connection already exists for your tenant.</span></span> <span data-ttu-id="92eec-134">Dans ce cas, exécutez la commande :</span><span class="sxs-lookup"><span data-stu-id="92eec-134">In this case, run the command:</span></span> 

   ```
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-skype-for-business-online-powershell-from-another-powershell-session-optional-method"></a><span data-ttu-id="92eec-135">Connectez-vous à Skype pour Business Online PowerShell à partir d’une autre session PowerShell (méthode facultatif)</span><span class="sxs-lookup"><span data-stu-id="92eec-135">Log in to Skype for Business Online PowerShell from another PowerShell session (optional method)</span></span>

1.  <span data-ttu-id="92eec-136">Si l’activation du connector pour la première fois, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="92eec-136">If enabling the connector for the first time, run the following command:</span></span> 

    ``` 
    New-CsCloudCallDataConnection 
    ```

2.  <span data-ttu-id="92eec-137">Si vous obtenez une erreur la connexion existe déjà, cela signifie que la connexion de données déjà appel existe pour votre client.</span><span class="sxs-lookup"><span data-stu-id="92eec-137">If you get an error that the connection already exists, this means that the call data connection already exists for your tenant.</span></span> <span data-ttu-id="92eec-138">Dans ce cas, exécutez la commande :</span><span class="sxs-lookup"><span data-stu-id="92eec-138">In this case, run the command:</span></span> 

    ```
    Get-CsCloudCallDataConnection  
    ```

<span data-ttu-id="92eec-139">La sortie des commandes ci-dessus contient une valeur de jeton dont vous aurez besoin lors de la configuration de votre environnement local comme suit :</span><span class="sxs-lookup"><span data-stu-id="92eec-139">The output of the above commands contains a token value, which you will need when configuring your on-premises environment as follows:</span></span>

<span data-ttu-id="92eec-140">À partir de dans la Skype pour shell de gestion Business Server, spécifiez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="92eec-140">From within the Skype for Business Server management shell, specify the following command:</span></span>

```
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a><span data-ttu-id="92eec-141">Configurer l’étendue</span><span class="sxs-lookup"><span data-stu-id="92eec-141">Configure the scope</span></span>

<span data-ttu-id="92eec-142">Vous pouvez activer le connecteur de données d’appel pour un site particulier ou pour votre ensemble Skype pour le déploiement de serveur d’entreprise à l’aide de l’applet de commande Set-CsCloudCallDataConnectorConfiguration à partir de la Skype pour shell de gestion Business Server.</span><span class="sxs-lookup"><span data-stu-id="92eec-142">You can enable Call Data Connector for a particular site or for your entire Skype for Business Server deployment by using the Set-CsCloudCallDataConnectorConfiguration cmdlet from within the Skype for Business Server management shell.</span></span> <span data-ttu-id="92eec-143">Par exemple, la commande suivante permet de connecteur de données d’appel dans l’étendue globale :</span><span class="sxs-lookup"><span data-stu-id="92eec-143">For example, the following command enables Call Data Connector at the global scope:</span></span>

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

<span data-ttu-id="92eec-144">En plus des paramètres globaux, les paramètres de configuration de connecteur de données d’appel peuvent être attribués au niveau du site.</span><span class="sxs-lookup"><span data-stu-id="92eec-144">In addition to the global settings, Call Data Connector configuration settings can be assigned to the site scope.</span></span> <span data-ttu-id="92eec-145">Cela offre la souplesse de gestion supplémentaires lorsqu’il s’agit de surveillance.</span><span class="sxs-lookup"><span data-stu-id="92eec-145">This provides additional management flexibility when it comes to monitoring.</span></span> <span data-ttu-id="92eec-146">Par exemple, un administrateur peut activer le transfert d’appel de connecteur de données pour le site Redmond mais désactiver le transfert d’appel de connecteur de données pour le site de Dublin, comme illustré dans l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="92eec-146">For example, an administrator can enable Call Data Connector forwarding for the Redmond site but disable Call Data Connector forwarding for the Dublin site, as shown in the following example:</span></span>

```
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

<span data-ttu-id="92eec-147">(Les paramètres configurés au niveau du site sont prioritaires sur les paramètres configurés au niveau global.)</span><span class="sxs-lookup"><span data-stu-id="92eec-147">Settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="92eec-148">Par exemple, supposons que le transfert d’appel de connecteur de données est activée dans l’étendue globale, mais désactivé au niveau du site (pour le site de Redmond).</span><span class="sxs-lookup"><span data-stu-id="92eec-148">For example, suppose Call Data Connector forwarding is enabled at the global scope, but disabled at the site scope (for the Redmond site).</span></span> <span data-ttu-id="92eec-149">Ce qui signifie que les appels enregistrement des détails et informations QoE n’est pas transférés pour les utilisateurs du site de Redmond.</span><span class="sxs-lookup"><span data-stu-id="92eec-149">That means that call detail recording and QoE information will not be forwarded for users in the Redmond site.</span></span> <span data-ttu-id="92eec-150">Cependant, les utilisateurs d’autres sites (autrement dit, les utilisateurs gérés par les paramètres globaux plutôt que les paramètres du site Redmond) auront leur enregistrement des détails des appels et les informations QoE transféré.</span><span class="sxs-lookup"><span data-stu-id="92eec-150">However, users in other sites (that is, users managed by the global settings instead of the Redmond site settings) will have their call detail recording and QoE information forwarded.</span></span>

<span data-ttu-id="92eec-151">Valeurs pour les paramètres fréquemment utilisés par le connecteur de données d’appel sont indiqués dans le tableau suivant :</span><span class="sxs-lookup"><span data-stu-id="92eec-151">Values for the most commonly used settings used by Call Data Connector are shown in the following table:</span></span>  

|<span data-ttu-id="92eec-152">Propriété</span><span class="sxs-lookup"><span data-stu-id="92eec-152">Property</span></span>|<span data-ttu-id="92eec-153">Description</span><span class="sxs-lookup"><span data-stu-id="92eec-153">Description</span></span>|<span data-ttu-id="92eec-154">Valeur par défaut</span><span class="sxs-lookup"><span data-stu-id="92eec-154">Default value</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="92eec-155">EnableCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="92eec-155">EnableCallDataConnector</span></span>  <br/> |<span data-ttu-id="92eec-156">Indique si le connecteur de données d’appel est activée.</span><span class="sxs-lookup"><span data-stu-id="92eec-156">Indicates whether Call Data Connector is enabled.</span></span> <span data-ttu-id="92eec-157">Si True, surveillance des enregistrements est transféré à l’analyse en ligne.</span><span class="sxs-lookup"><span data-stu-id="92eec-157">If True, monitoring records will be forwarded to online monitoring.</span></span>  <br/> |<span data-ttu-id="92eec-158">$False</span><span class="sxs-lookup"><span data-stu-id="92eec-158">$False</span></span>  <br/> |
| <span data-ttu-id="92eec-159">Identity </span><span class="sxs-lookup"><span data-stu-id="92eec-159">Identity</span></span> | <span data-ttu-id="92eec-160">Détermine le niveau de l’étendue de la commande : global ou site.</span><span class="sxs-lookup"><span data-stu-id="92eec-160">Determines the scope level for the command: global or site.</span></span>   | <span data-ttu-id="92eec-161">global</span><span class="sxs-lookup"><span data-stu-id="92eec-161">global</span></span>  |

## <a name="disable-call-data-connector"></a><span data-ttu-id="92eec-162">Désactiver le connecteur de données d’appel</span><span class="sxs-lookup"><span data-stu-id="92eec-162">Disable Call Data Connector</span></span>

<span data-ttu-id="92eec-163">Désactivation de connecteur de données d’appel dissocier pas au magasin d’analyse à partir du pool frontal, ni ne désinstaller affecter la base de données de surveillance de serveur principal.</span><span class="sxs-lookup"><span data-stu-id="92eec-163">Disabling Call Data Connector does not disassociate the monitoring store from the Front End pool, nor does it uninstall or otherwise affect the backend monitoring database.</span></span> <span data-ttu-id="92eec-164">Lorsque vous désactivez le connecteur de données d’appel, vous arrêtez Skype pour Business Server à partir du téléchargement de données de l’appel vers le nuage.</span><span class="sxs-lookup"><span data-stu-id="92eec-164">When you disable Call Data Connector, you stop Skype for Business Server from uploading call data to the cloud.</span></span> 

<span data-ttu-id="92eec-165">Vous désactivez appeler un connecteur de données à l’aide de l’applet de commande Set-CsCloudCallDataConnectorConfiguration à partir de la Skype pour shell de gestion Business Server.</span><span class="sxs-lookup"><span data-stu-id="92eec-165">You disable Call Data Connector by using the Set-CsCloudCallDataConnectorConfiguration cmdlet from within the Skype for Business Server management shell.</span></span> <span data-ttu-id="92eec-166">Par exemple, la commande suivante désactive le connecteur de données d’appel dans l’étendue globale en définissant la propriété EnableCallDataConnector sur $False :</span><span class="sxs-lookup"><span data-stu-id="92eec-166">For example, the following command disables Call Data Connector at the global scope by setting the EnableCallDataConnector property to $False:</span></span>

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

<span data-ttu-id="92eec-167">Si vous souhaitez reprendre le téléchargement des données d’appel vers le nuage, définissez la propriété EnableCallDataConnector sur $True, comme illustré dans l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="92eec-167">If you want to resume uploading call data to the cloud, set the EnableCallDataConnector property back to $True, as shown in the following example:</span></span>

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a><span data-ttu-id="92eec-168">Affichage de données via le tableau de bord en ligne sur site</span><span class="sxs-lookup"><span data-stu-id="92eec-168">View on-premises data through the online dashboard</span></span>

 <span data-ttu-id="92eec-169">Une fois que le connecteur de données d’appel est activé, vous pouvez afficher vos données d’appel local sur le tableau de bord Analytique appel comme décrit dans [Utilisation appeler Analytique pour résoudre les problèmes de qualité médiocre](https://docs.microsoft.com/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality).</span><span class="sxs-lookup"><span data-stu-id="92eec-169">After Call Data Connector is enabled, you can view your on-premises call data on the Call Analytics dashboard as described in  [Use Call Analytics to troubleshoot poor quality](https://docs.microsoft.com/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality).</span></span>


## <a name="for-more-information"></a><span data-ttu-id="92eec-170">Pour plus d’informations</span><span class="sxs-lookup"><span data-stu-id="92eec-170">For more information</span></span>

<span data-ttu-id="92eec-171">Pour plus d’informations sur les applets de commande, vous pouvez utiliser la commande Get-Help le Skype pour Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="92eec-171">For more information on the cmdlets, you can use the Get-Help command from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="92eec-172">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="92eec-172">For example:</span></span>

<span data-ttu-id="92eec-173">Get-Help Get-CsCloudCallDataConnector | plus</span><span class="sxs-lookup"><span data-stu-id="92eec-173">Get-Help Get-CsCloudCallDataConnector | more</span></span>

<span data-ttu-id="92eec-174">Get-Help Set-CsCloudCallDataConnector | plus</span><span class="sxs-lookup"><span data-stu-id="92eec-174">Get-Help Set-CsCloudCallDataConnector | more</span></span>

<span data-ttu-id="92eec-175">Get-Help Set-CsCloudCallDataConnectorConfiguration | plus</span><span class="sxs-lookup"><span data-stu-id="92eec-175">Get-Help Set-CsCloudCallDataConnectorConfiguration | more</span></span>