---
title: Configurer le connecteur de données d’appel
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Instructions pour la configuration du connecteur de données d’appel, qui permet d’afficher la télémétrie à partir de Skype entreprise en local à l’aide des outils Skype entreprise online.
ms.openlocfilehash: 0354f5a1fd1b4794af29d23e0a0fc1bf49dfebd2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726924"
---
# <a name="configure-call-data-connector"></a><span data-ttu-id="1dcec-103">Configurer le connecteur de données d’appel</span><span class="sxs-lookup"><span data-stu-id="1dcec-103">Configure Call Data Connector</span></span>

<span data-ttu-id="1dcec-104">Cet article explique comment configurer le connecteur de données d’appel, un seul ensemble d’outils qui permet d’afficher les données de qualité des appels de Skype entreprise Server à l’aide des outils de tableau de bord de qualité des appels de Skype entreprise Online (CQD) et des outils d’analyse des appels.</span><span class="sxs-lookup"><span data-stu-id="1dcec-104">This article describes how to configure Call Data Connector--a single toolset that enables viewing Skype for Business Server Call Quality Data using Skype for Business Online Call Quality Dashboard (CQD) and Call Analytics (CA) tools.</span></span>

<span data-ttu-id="1dcec-105">Pour plus d’informations sur les avantages et les conditions préalables du connecteur de données d’appel, tels que les exigences de rôle et la configuration de la connectivité hybride, voir [plan Call Data Connector](plan-call-data-connector.md).</span><span class="sxs-lookup"><span data-stu-id="1dcec-105">For more information about Call Data Connector benefits and pre-requisites, such as role requirements and setting up hybrid connectivity, see [Plan Call Data Connector](plan-call-data-connector.md).</span></span>

## <a name="enable-monitoring"></a><span data-ttu-id="1dcec-106">Activer la surveillance</span><span class="sxs-lookup"><span data-stu-id="1dcec-106">Enable Monitoring</span></span>
 
<span data-ttu-id="1dcec-107">Vous devez configurer la collecte de données d’enregistrement des données d’appels (CDR) et de qualité de l’expérience (QoE) dans votre surveillance de pool frontal, avec des bases de données LCSCdr et QoEMetrics locales ; dans le cas contraire, les tableaux de bord d’analyse de l’appel et de qualité des appels n’obtiendront pas de données à utiliser.</span><span class="sxs-lookup"><span data-stu-id="1dcec-107">You must configure Call Data Recording (CDR) and Quality of Experience (QoE) data collection in your front end pool Monitoring,with local LCSCdr and QoEMetrics databases; otherwise, the Call Analytics and Call Quality Dashboards won’t get data to work with.</span></span> <span data-ttu-id="1dcec-108">Avant de configurer le connecteur de données d’appel, suivez les étapes décrites dans [Deploy Monitoring in Skype for Business Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) pour configurer à la fois les enregistrements CDR et QoE, ainsi que la surveillance de base.</span><span class="sxs-lookup"><span data-stu-id="1dcec-108">Before you Configure Call Data Connector, follow the steps provided in [Deploy monitoring in Skype for Business Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) to configure both CDR and QoE as well as basic Monitoring.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1dcec-109">Le connecteur de données d’appel ne fonctionne pas si la surveillance n’est pas activée sur le pool frontal.</span><span class="sxs-lookup"><span data-stu-id="1dcec-109">Call Data Connector will not function if Monitoring is not enabled on the front end pool.</span></span>

## <a name="enable-call-data-connector"></a><span data-ttu-id="1dcec-110">Activer le connecteur de données d’appel</span><span class="sxs-lookup"><span data-stu-id="1dcec-110">Enable Call Data Connector</span></span>

<span data-ttu-id="1dcec-111">Pour configurer et activer le connecteur de données d’appel, vous devez utiliser les applets de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="1dcec-111">To configure and enable Call Data Connector, you will use the following cmdlets:</span></span>

| <span data-ttu-id="1dcec-112">Applet de commande</span><span class="sxs-lookup"><span data-stu-id="1dcec-112">Cmdlet</span></span>| <span data-ttu-id="1dcec-113">Description</span><span class="sxs-lookup"><span data-stu-id="1dcec-113">Description</span></span>|
| :-----------------|---------------:|
| <span data-ttu-id="1dcec-114">New-CsCloudCallDataConnection</span><span class="sxs-lookup"><span data-stu-id="1dcec-114">New-CsCloudCallDataConnection</span></span> | <span data-ttu-id="1dcec-115">Cmdlet en ligne qui établit un collecteur de données en ligne.</span><span class="sxs-lookup"><span data-stu-id="1dcec-115">An online cmdlet that establishes an online data collector.</span></span>|
| <span data-ttu-id="1dcec-116">Get-CsCloudCallDataConnection</span><span class="sxs-lookup"><span data-stu-id="1dcec-116">Get-CsCloudCallDataConnection</span></span> | <span data-ttu-id="1dcec-117">Cmdlet en ligne qui récupère un collecteur de données en ligne existant.</span><span class="sxs-lookup"><span data-stu-id="1dcec-117">An online cmdlet that retrieves an existing online data collector.</span></span>|  
| <span data-ttu-id="1dcec-118">Get-CsCloudCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="1dcec-118">Get-CsCloudCallDataConnector</span></span> | <span data-ttu-id="1dcec-119">Une cmdlet locale qui récupère les informations de connexion créées par la cmdlet New-CsCloudCallDataConnection.</span><span class="sxs-lookup"><span data-stu-id="1dcec-119">An on-premises cmdlet that retrieves the connection information created by the New-CsCloudCallDataConnection cmdlet.</span></span> |
| <span data-ttu-id="1dcec-120">Set-CsCloudCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="1dcec-120">Set-CsCloudCallDataConnector</span></span> | <span data-ttu-id="1dcec-121">Une applet de commande locale qui enregistre une copie locale des informations de connexion créées par la cmdlet New-CsCloudCallDataConnection.</span><span class="sxs-lookup"><span data-stu-id="1dcec-121">An on-premises cmdlet that saves an on-premises copy of the connection information created by the New-CsCloudCallDataConnection cmdlet.</span></span> |  
| <span data-ttu-id="1dcec-122">Set-CsCloudCallDataConnectorConfiguration</span><span class="sxs-lookup"><span data-stu-id="1dcec-122">Set-CsCloudCallDataConnectorConfiguration</span></span> | <span data-ttu-id="1dcec-123">Une applet de commande locale qui vous permet d’activer ou de désactiver le connecteur et de personnaliser le niveau d’étendue.</span><span class="sxs-lookup"><span data-stu-id="1dcec-123">An on-premises cmdlet that allows you to enable or disable the connector and customize the scope level.</span></span>|

> [!NOTE]
> <span data-ttu-id="1dcec-124">Pour effacer votre configuration et recommencer, utilisez la cmdlet Remove-csclouddatconnectorconfiguration.</span><span class="sxs-lookup"><span data-stu-id="1dcec-124">To erase your configuration and start over, please use the Remove-csclouddatconnectorconfiguration cmdlet.</span></span>

### <a name="configure-your-environment"></a><span data-ttu-id="1dcec-125">Configurer votre environnement</span><span class="sxs-lookup"><span data-stu-id="1dcec-125">Configure your environment</span></span> 

<span data-ttu-id="1dcec-126">Pour configurer votre environnement afin d’activer un collecteur de données en ligne, vous devez d’abord vous connecter à Skype entreprise Online PowerShell en tant qu’administrateur.</span><span class="sxs-lookup"><span data-stu-id="1dcec-126">To configure your environment to enable an online data collector, you must first log in to Skype for Business Online PowerShell as an administrator.</span></span> <span data-ttu-id="1dcec-127">Pour plus d’informations, reportez-vous à la rubrique [Manage Skype for Business Online with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="1dcec-127">For more information, see [Manage Skype for Business Online with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

<span data-ttu-id="1dcec-128">Il existe deux méthodes pour vous connecter à Skype entreprise Online PowerShell :</span><span class="sxs-lookup"><span data-stu-id="1dcec-128">There are two methods for logging in to Skype for Business Online PowerShell:</span></span>

- <span data-ttu-id="1dcec-129">À partir de Skype entreprise Server 2019 Management Shell (méthode recommandée)</span><span class="sxs-lookup"><span data-stu-id="1dcec-129">From the Skype for Business Server 2019 management shell (recommended method)</span></span>
- <span data-ttu-id="1dcec-130">À partir d’une autre session PowerShell</span><span class="sxs-lookup"><span data-stu-id="1dcec-130">From another PowerShell session</span></span>

#### <a name="log-in-to-skype-for-business-online-powershell-from-the-skype-for-business-server-management-shell-recommended-method"></a><span data-ttu-id="1dcec-131">Connectez-vous à Skype entreprise Online PowerShell à partir de Skype entreprise Server Management Shell (méthode recommandée).</span><span class="sxs-lookup"><span data-stu-id="1dcec-131">Log in to Skype for Business Online PowerShell from the Skype for Business Server management shell (recommended method)</span></span>

1. <span data-ttu-id="1dcec-132">Si vous activez le connecteur pour la première fois, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="1dcec-132">If enabling the connector for the first time, run the following command:</span></span>

   ```PowerShell
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. <span data-ttu-id="1dcec-133">Si vous obtenez une erreur indiquant que la connexion existe déjà, cela signifie que la connexion de données d’appel existe déjà pour votre client.</span><span class="sxs-lookup"><span data-stu-id="1dcec-133">If you get an error that the connection already exists, this means that the call data connection already exists for your tenant.</span></span> <span data-ttu-id="1dcec-134">Dans ce cas, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="1dcec-134">In this case, run the command:</span></span> 

   ```PowerShell
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-skype-for-business-online-powershell-from-another-powershell-session-optional-method"></a><span data-ttu-id="1dcec-135">Se connecter à Skype entreprise Online PowerShell à partir d’une autre session PowerShell (méthode facultative)</span><span class="sxs-lookup"><span data-stu-id="1dcec-135">Log in to Skype for Business Online PowerShell from another PowerShell session (optional method)</span></span>

1.  <span data-ttu-id="1dcec-136">Si vous activez le connecteur pour la première fois, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="1dcec-136">If enabling the connector for the first time, run the following command:</span></span> 

    ```PowerShell 
    New-CsCloudCallDataConnection 
    ```

2.  <span data-ttu-id="1dcec-137">Si vous obtenez une erreur indiquant que la connexion existe déjà, cela signifie que la connexion de données d’appel existe déjà pour votre client.</span><span class="sxs-lookup"><span data-stu-id="1dcec-137">If you get an error that the connection already exists, this means that the call data connection already exists for your tenant.</span></span> <span data-ttu-id="1dcec-138">Dans ce cas, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="1dcec-138">In this case, run the command:</span></span> 

    ```PowerShell
    Get-CsCloudCallDataConnection  
    ```

<span data-ttu-id="1dcec-139">La sortie des commandes ci-dessus contient une valeur de jeton, dont vous aurez besoin lors de la configuration de votre environnement local comme suit :</span><span class="sxs-lookup"><span data-stu-id="1dcec-139">The output of the above commands contains a token value, which you will need when configuring your on-premises environment as follows:</span></span>

<span data-ttu-id="1dcec-140">À partir de Skype entreprise Server Management Shell, spécifiez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="1dcec-140">From within the Skype for Business Server management shell, specify the following command:</span></span>

```PowerShell
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a><span data-ttu-id="1dcec-141">Configurer l’étendue</span><span class="sxs-lookup"><span data-stu-id="1dcec-141">Configure the scope</span></span>

<span data-ttu-id="1dcec-142">Vous pouvez activer le connecteur de données d’appel pour un site particulier ou pour votre déploiement de Skype entreprise Server entier à l’aide de la cmdlet Set-CsCloudCallDataConnectorConfiguration à partir de Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="1dcec-142">You can enable Call Data Connector for a particular site or for your entire Skype for Business Server deployment by using the Set-CsCloudCallDataConnectorConfiguration cmdlet from within the Skype for Business Server management shell.</span></span> <span data-ttu-id="1dcec-143">Par exemple, la commande suivante active le connecteur de données d’appel au niveau global :</span><span class="sxs-lookup"><span data-stu-id="1dcec-143">For example, the following command enables Call Data Connector at the global scope:</span></span>

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

<span data-ttu-id="1dcec-144">En plus des paramètres globaux, les paramètres de configuration du connecteur de données d’appel peuvent être affectés à l’étendue site.</span><span class="sxs-lookup"><span data-stu-id="1dcec-144">In addition to the global settings, Call Data Connector configuration settings can be assigned to the site scope.</span></span> <span data-ttu-id="1dcec-145">Cela offre davantage de souplesse de gestion en matière de surveillance.</span><span class="sxs-lookup"><span data-stu-id="1dcec-145">This provides additional management flexibility when it comes to monitoring.</span></span> <span data-ttu-id="1dcec-146">Par exemple, un administrateur peut activer le transfert du connecteur de données d’appel pour le site de Redmond, mais désactiver le transfert du connecteur de données d’appel pour le site Dublin, comme illustré dans l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="1dcec-146">For example, an administrator can enable Call Data Connector forwarding for the Redmond site but disable Call Data Connector forwarding for the Dublin site, as shown in the following example:</span></span>

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

<span data-ttu-id="1dcec-147">(Les paramètres configurés au niveau du site sont prioritaires sur les paramètres configurés au niveau global.)</span><span class="sxs-lookup"><span data-stu-id="1dcec-147">Settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="1dcec-148">Par exemple, supposons que le transfert du connecteur de données d’appel est activé au niveau de l’étendue globale, mais désactivé au niveau de l’étendue du site (pour le site Redmond).</span><span class="sxs-lookup"><span data-stu-id="1dcec-148">For example, suppose Call Data Connector forwarding is enabled at the global scope, but disabled at the site scope (for the Redmond site).</span></span> <span data-ttu-id="1dcec-149">Cela signifie que l’enregistrement des détails des appels et les informations QoE ne seront pas transférés pour les utilisateurs du site Redmond.</span><span class="sxs-lookup"><span data-stu-id="1dcec-149">That means that call detail recording and QoE information will not be forwarded for users in the Redmond site.</span></span> <span data-ttu-id="1dcec-150">Toutefois, les utilisateurs d’autres sites (c’est-à-dire, les utilisateurs gérés par les paramètres globaux au lieu des paramètres du site de Redmond) disposeront de l’enregistrement des détails des appels et des informations QoE transmises.</span><span class="sxs-lookup"><span data-stu-id="1dcec-150">However, users in other sites (that is, users managed by the global settings instead of the Redmond site settings) will have their call detail recording and QoE information forwarded.</span></span>

<span data-ttu-id="1dcec-151">Les valeurs des paramètres les plus fréquemment utilisés utilisés par le connecteur de données d’appel sont indiquées dans le tableau suivant :</span><span class="sxs-lookup"><span data-stu-id="1dcec-151">Values for the most commonly used settings used by Call Data Connector are shown in the following table:</span></span>  

|<span data-ttu-id="1dcec-152">Propriété</span><span class="sxs-lookup"><span data-stu-id="1dcec-152">Property</span></span>|<span data-ttu-id="1dcec-153">Description</span><span class="sxs-lookup"><span data-stu-id="1dcec-153">Description</span></span>|<span data-ttu-id="1dcec-154">Valeur par défaut</span><span class="sxs-lookup"><span data-stu-id="1dcec-154">Default value</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1dcec-155">EnableCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="1dcec-155">EnableCallDataConnector</span></span>  <br/> |<span data-ttu-id="1dcec-156">Indique si le connecteur de données d’appel est activé.</span><span class="sxs-lookup"><span data-stu-id="1dcec-156">Indicates whether Call Data Connector is enabled.</span></span> <span data-ttu-id="1dcec-157">Si la valeur est true, les enregistrements de surveillance sont transférés vers la surveillance en ligne.</span><span class="sxs-lookup"><span data-stu-id="1dcec-157">If True, monitoring records will be forwarded to online monitoring.</span></span>  <br/> |<span data-ttu-id="1dcec-158">$False</span><span class="sxs-lookup"><span data-stu-id="1dcec-158">$False</span></span>  <br/> |
| <span data-ttu-id="1dcec-159">Identité</span><span class="sxs-lookup"><span data-stu-id="1dcec-159">Identity</span></span> | <span data-ttu-id="1dcec-160">Détermine le niveau d’étendue de la commande : global ou site.</span><span class="sxs-lookup"><span data-stu-id="1dcec-160">Determines the scope level for the command: global or site.</span></span>   | <span data-ttu-id="1dcec-161">Global</span><span class="sxs-lookup"><span data-stu-id="1dcec-161">global</span></span>  |

## <a name="disable-call-data-connector"></a><span data-ttu-id="1dcec-162">Désactiver le connecteur de données d’appel</span><span class="sxs-lookup"><span data-stu-id="1dcec-162">Disable Call Data Connector</span></span>

<span data-ttu-id="1dcec-163">La désactivation du connecteur de données d’appel ne dissocie pas le magasin de surveillance du pool frontal et ne désinstalle pas ou n’affecte pas la base de données de surveillance principale.</span><span class="sxs-lookup"><span data-stu-id="1dcec-163">Disabling Call Data Connector does not disassociate the monitoring store from the Front End pool, nor does it uninstall or otherwise affect the backend monitoring database.</span></span> <span data-ttu-id="1dcec-164">Lorsque vous désactivez le connecteur de données d’appel, vous empêchez Skype entreprise Server de télécharger des données d’appel vers le Cloud.</span><span class="sxs-lookup"><span data-stu-id="1dcec-164">When you disable Call Data Connector, you stop Skype for Business Server from uploading call data to the cloud.</span></span> 

<span data-ttu-id="1dcec-165">Vous désactivez le connecteur de données d’appel à l’aide de la cmdlet Set-CsCloudCallDataConnectorConfiguration à partir de Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="1dcec-165">You disable Call Data Connector by using the Set-CsCloudCallDataConnectorConfiguration cmdlet from within the Skype for Business Server management shell.</span></span> <span data-ttu-id="1dcec-166">Par exemple, la commande suivante désactive le connecteur de données d’appel au niveau de l’étendue globale en définissant la propriété EnableCallDataConnector sur $False :</span><span class="sxs-lookup"><span data-stu-id="1dcec-166">For example, the following command disables Call Data Connector at the global scope by setting the EnableCallDataConnector property to $False:</span></span>

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

<span data-ttu-id="1dcec-167">Si vous souhaitez reprendre le téléchargement des données d’appel vers le Cloud, redéfinissez la propriété EnableCallDataConnector sur $True, comme illustré dans l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="1dcec-167">If you want to resume uploading call data to the cloud, set the EnableCallDataConnector property back to $True, as shown in the following example:</span></span>

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a><span data-ttu-id="1dcec-168">Afficher les données locales via le tableau de bord en ligne</span><span class="sxs-lookup"><span data-stu-id="1dcec-168">View on-premises data through the online dashboard</span></span>

 <span data-ttu-id="1dcec-169">Une fois que le connecteur de données d’appel est activé, vous pouvez afficher vos données d’appel locales sur le tableau de bord d’analyse des appels ou sur la qualité des appels, comme décrit dans [utiliser l’analyse des appels pour résoudre les problèmes de qualité médiocre](https://docs.microsoft.com/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality) et [activer et utiliser le tableau de bord de qualité des appels pour Microsoft teams et Skype entreprise Online](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard).</span><span class="sxs-lookup"><span data-stu-id="1dcec-169">After Call Data Connector is enabled, you can view your on-premises call data on the Call Analytics dashboard or Call Quality Dashboard as described in  [Use Call Analytics to troubleshoot poor quality](https://docs.microsoft.com/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality) and [Turn on and use Call Quality Dashboard for Microsoft Teams and Skype for Business Online](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="1dcec-170">Pour plus d'informations</span><span class="sxs-lookup"><span data-stu-id="1dcec-170">For more information</span></span>

<span data-ttu-id="1dcec-171">Pour plus d’informations sur les cmdlets, vous pouvez utiliser la commande Get-Help à partir de Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="1dcec-171">For more information on the cmdlets, you can use the Get-Help command from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="1dcec-172">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="1dcec-172">For example:</span></span>

<span data-ttu-id="1dcec-173">Get-Help Get-CsCloudCallDataConnector | plus d'</span><span class="sxs-lookup"><span data-stu-id="1dcec-173">Get-Help Get-CsCloudCallDataConnector | more</span></span>

<span data-ttu-id="1dcec-174">Get-Help Set-CsCloudCallDataConnector | plus d'</span><span class="sxs-lookup"><span data-stu-id="1dcec-174">Get-Help Set-CsCloudCallDataConnector | more</span></span>

<span data-ttu-id="1dcec-175">Get-Help Set-CsCloudCallDataConnectorConfiguration | plus d'</span><span class="sxs-lookup"><span data-stu-id="1dcec-175">Get-Help Set-CsCloudCallDataConnectorConfiguration | more</span></span>
