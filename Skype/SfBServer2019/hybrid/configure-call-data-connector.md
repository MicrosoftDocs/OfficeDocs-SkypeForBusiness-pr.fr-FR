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
ms.openlocfilehash: 38e74e76e09d03036419f16807841a67fdf3433a
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "25030573"
---
# <a name="configure-call-data-connector"></a><span data-ttu-id="5ab47-103">Configurer le connecteur de données d’appel</span><span class="sxs-lookup"><span data-stu-id="5ab47-103">Configure Call Data Connector</span></span>

[!INCLUDE [disclaimer](../disclaimer.md)]

<span data-ttu-id="5ab47-104">Cet article décrit comment configurer le connecteur de données d’appel : un ensemble d’outils unique qui permet l’affichage Skype pour serveur appeler la qualité des données métiers à l’aide de Skype des outils Business Online appeler qualité du tableau de bord (CQD) et appelez Analytique (CA).</span><span class="sxs-lookup"><span data-stu-id="5ab47-104">This article describes how to configure Call Data Connector--a single toolset that enables viewing Skype for Business Server Call Quality Data using Skype for Business Online Call Quality Dashboard (CQD) and Call Analytics (CA) tools.</span></span> 

> [!NOTE]
> <span data-ttu-id="5ab47-105">Version d’évaluation, tableau de bord Analytique appeler uniquement est disponible.</span><span class="sxs-lookup"><span data-stu-id="5ab47-105">At public preview release, only Call Analytics dashboard is available.</span></span>

<span data-ttu-id="5ab47-106">Pour plus d’informations sur les avantages de l’appel de connecteur de données et les composants requis, tels que les exigences de rôle et la configuration de la connectivité hybride, voir [Planification de connecteur de données d’appel](plan-call-data-connector.md).</span><span class="sxs-lookup"><span data-stu-id="5ab47-106">For more information about Call Data Connector benefits and pre-requisites, such as role requirements and setting up hybrid connectivity, see [Plan Call Data Connector](plan-call-data-connector.md).</span></span>

## <a name="enable-monitoring"></a><span data-ttu-id="5ab47-107">Activer la surveillance</span><span class="sxs-lookup"><span data-stu-id="5ab47-107">Enable Monitoring</span></span> 

<span data-ttu-id="5ab47-108">Vous devez configurer la collecte de données de qualité de l’expérience (QoE) ; et d’enregistrement de données des appels (CDR) dans le cas contraire, l’Analytique d’appel et appel des tableaux de bord qualité ne sont pas obtenir des informations à afficher.</span><span class="sxs-lookup"><span data-stu-id="5ab47-108">You must configure Call Data Recording (CDR) and Quality of Experience (QoE) data collection; otherwise, the Call Analytics and Call Quality Dashboards won’t get information to display.</span></span> <span data-ttu-id="5ab47-109">Avant que vous configurer appel données connecteur, suivez les étapes fournies dans [Deploy surveillance dans Skype pour Business Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) pour configurer des détails des appels et QoE.</span><span class="sxs-lookup"><span data-stu-id="5ab47-109">Before you Configure Call Data Connector, follow the steps provided in [Deploy monitoring in Skype for Business Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) to configure both CDR and QoE.</span></span>


## <a name="enable-call-data-connector"></a><span data-ttu-id="5ab47-110">Activer le connecteur de données d’appel</span><span class="sxs-lookup"><span data-stu-id="5ab47-110">Enable Call Data Connector</span></span>

<span data-ttu-id="5ab47-111">Pour configurer et activer le connecteur de données d’appel, vous allez utiliser les applets de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="5ab47-111">To configure and enable Call Data Connector, you will use the following cmdlets:</span></span>

| <span data-ttu-id="5ab47-112">Applet de commande</span><span class="sxs-lookup"><span data-stu-id="5ab47-112">Cmdlet</span></span>| <span data-ttu-id="5ab47-113">Description</span><span class="sxs-lookup"><span data-stu-id="5ab47-113">Description</span></span>|
| :-----------------|---------------:|
| <span data-ttu-id="5ab47-114">Nouvelle CsCloudCallDataConnection</span><span class="sxs-lookup"><span data-stu-id="5ab47-114">New-CsCloudCallDataConnection</span></span> | <span data-ttu-id="5ab47-115">Une applet de commande en ligne qui établit un collecteur de données en ligne.</span><span class="sxs-lookup"><span data-stu-id="5ab47-115">An online cmdlet that establishes an online data collector.</span></span>|
| <span data-ttu-id="5ab47-116">Get-CsCloudCallDataConnection</span><span class="sxs-lookup"><span data-stu-id="5ab47-116">Get-CsCloudCallDataConnection</span></span> | <span data-ttu-id="5ab47-117">Une applet de commande en ligne qui Récupère un collecteur de données en ligne existant.</span><span class="sxs-lookup"><span data-stu-id="5ab47-117">An online cmdlet that retrieves an existing online data collector.</span></span>|  
| <span data-ttu-id="5ab47-118">Get-CsCloudCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="5ab47-118">Get-CsCloudCallDataConnector</span></span> | <span data-ttu-id="5ab47-119">Applet de commande locale qui Récupère les informations de connexion créées par l’applet de commande New-CsCloudCallDataConnection.</span><span class="sxs-lookup"><span data-stu-id="5ab47-119">An on-premises cmdlet that retrieves the connection information created by the New-CsCloudCallDataConnection cmdlet.</span></span> |
| <span data-ttu-id="5ab47-120">Set-CsCloudCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="5ab47-120">Set-CsCloudCallDataConnector</span></span> | <span data-ttu-id="5ab47-121">Applet de commande locale qui permet d’enregistrer une copie locale, les informations de connexion créées par l’applet de commande New-CsCloudCallDataConnection.</span><span class="sxs-lookup"><span data-stu-id="5ab47-121">An on-premises cmdlet that saves an on-premises copy of the connection information created by the New-CsCloudCallDataConnection cmdlet.</span></span> |  
| <span data-ttu-id="5ab47-122">Set-CsCloudCallDataConnectorConfiguration</span><span class="sxs-lookup"><span data-stu-id="5ab47-122">Set-CsCloudCallDataConnectorConfiguration</span></span> | <span data-ttu-id="5ab47-123">Applet de commande locale qui permet d’activer ou désactiver le connecteur et personnaliser le niveau de l’étendue.</span><span class="sxs-lookup"><span data-stu-id="5ab47-123">An on-premises cmdlet that allows you to enable or disable the connector and customize the scope level.</span></span>|

### <a name="configure-your-environment"></a><span data-ttu-id="5ab47-124">Configurer votre environnement</span><span class="sxs-lookup"><span data-stu-id="5ab47-124">Configure your environment</span></span> 

<span data-ttu-id="5ab47-125">Pour configurer votre environnement pour activer un collecteur de données en ligne, vous devez tout d’abord vous connecter à Skype pour Business Online PowerShell en tant qu’administrateur.</span><span class="sxs-lookup"><span data-stu-id="5ab47-125">To configure your environment to enable an online data collector, you must first log in to Skype for Business Online PowerShell as an administrator.</span></span> <span data-ttu-id="5ab47-126">Pour plus d’informations, voir [Gérer les Skype pour Business en ligne avec Office 365 PowerShell](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="5ab47-126">For more information, see [Manage Skype for Business Online with Office 365 PowerShell](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

<span data-ttu-id="5ab47-127">Il existe deux méthodes pour la connexion à Skype pour Business Online PowerShell :</span><span class="sxs-lookup"><span data-stu-id="5ab47-127">There are two methods for logging in to Skype for Business Online PowerShell:</span></span>

- <span data-ttu-id="5ab47-128">À partir de la Skype pour Business Server 2019 management shell (méthode recommandée)</span><span class="sxs-lookup"><span data-stu-id="5ab47-128">From the Skype for Business Server 2019 management shell (recommended method)</span></span>
- <span data-ttu-id="5ab47-129">À partir d’une autre session PowerShell</span><span class="sxs-lookup"><span data-stu-id="5ab47-129">From another PowerShell session</span></span>

#### <a name="log-in-to-skype-for-business-online-powershell-from-the-skype-for-business-server-management-shell-recommended-method"></a><span data-ttu-id="5ab47-130">Connectez-vous à Skype pour Business Online PowerShell à partir de la Skype pour Business Server management shell (méthode recommandée)</span><span class="sxs-lookup"><span data-stu-id="5ab47-130">Log in to Skype for Business Online PowerShell from the Skype for Business Server management shell (recommended method)</span></span>

1. <span data-ttu-id="5ab47-131">Si l’activation du connector pour la première fois, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="5ab47-131">If enabling the connector for the first time, run the following command:</span></span>

   ```
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. <span data-ttu-id="5ab47-132">Si vous obtenez une erreur la connexion existe déjà, cela signifie que la connexion de données déjà appel existe pour votre client.</span><span class="sxs-lookup"><span data-stu-id="5ab47-132">If you get an error that the connection already exists, this means that the call data connection already exists for your tenant.</span></span> <span data-ttu-id="5ab47-133">Dans ce cas, exécutez la commande :</span><span class="sxs-lookup"><span data-stu-id="5ab47-133">In this case, run the command:</span></span> 

   ```
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-skype-for-business-online-powershell-from-another-powershell-session-optional-method"></a><span data-ttu-id="5ab47-134">Connectez-vous à Skype pour Business Online PowerShell à partir d’une autre session PowerShell (méthode facultatif)</span><span class="sxs-lookup"><span data-stu-id="5ab47-134">Log in to Skype for Business Online PowerShell from another PowerShell session (optional method)</span></span>

1.  <span data-ttu-id="5ab47-135">Si l’activation du connector pour la première fois, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="5ab47-135">If enabling the connector for the first time, run the following command:</span></span> 

    ``` 
    New-CsCloudCallDataConnection 
    ```

2.  <span data-ttu-id="5ab47-136">Si vous obtenez une erreur la connexion existe déjà, cela signifie que la connexion de données déjà appel existe pour votre client.</span><span class="sxs-lookup"><span data-stu-id="5ab47-136">If you get an error that the connection already exists, this means that the call data connection already exists for your tenant.</span></span> <span data-ttu-id="5ab47-137">Dans ce cas, exécutez la commande :</span><span class="sxs-lookup"><span data-stu-id="5ab47-137">In this case, run the command:</span></span> 

    ```
    Get-CsCloudCallDataConnection  
    ```

<span data-ttu-id="5ab47-138">La sortie des commandes ci-dessus contient une valeur de jeton dont vous aurez besoin lors de la configuration de votre environnement local comme suit :</span><span class="sxs-lookup"><span data-stu-id="5ab47-138">The output of the above commands contains a token value, which you will need when configuring your on-premises environment as follows:</span></span>

<span data-ttu-id="5ab47-139">À partir de dans la Skype pour shell de gestion Business Server, spécifiez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="5ab47-139">From within the Skype for Business Server management shell, specify the following command:</span></span>

```
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a><span data-ttu-id="5ab47-140">Configurer l’étendue</span><span class="sxs-lookup"><span data-stu-id="5ab47-140">Configure the scope</span></span>

<span data-ttu-id="5ab47-141">Vous pouvez activer le connecteur de données d’appel pour un site particulier ou pour votre ensemble Skype pour le déploiement de serveur d’entreprise à l’aide de l’applet de commande Set-CsCloudCallDataConnectorConfiguration à partir de la Skype pour shell de gestion Business Server.</span><span class="sxs-lookup"><span data-stu-id="5ab47-141">You can enable Call Data Connector for a particular site or for your entire Skype for Business Server deployment by using the Set-CsCloudCallDataConnectorConfiguration cmdlet from within the Skype for Business Server management shell.</span></span> <span data-ttu-id="5ab47-142">Par exemple, la commande suivante permet de connecteur de données d’appel dans l’étendue globale :</span><span class="sxs-lookup"><span data-stu-id="5ab47-142">For example, the following command enables Call Data Connector at the global scope:</span></span>

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

<span data-ttu-id="5ab47-143">En plus des paramètres globaux, les paramètres de configuration de connecteur de données d’appel peuvent être attribués au niveau du site.</span><span class="sxs-lookup"><span data-stu-id="5ab47-143">In addition to the global settings, Call Data Connector configuration settings can be assigned to the site scope.</span></span> <span data-ttu-id="5ab47-144">Cela offre la souplesse de gestion supplémentaires lorsqu’il s’agit de surveillance.</span><span class="sxs-lookup"><span data-stu-id="5ab47-144">This provides additional management flexibility when it comes to monitoring.</span></span> <span data-ttu-id="5ab47-145">Par exemple, un administrateur peut activer le transfert d’appel de connecteur de données pour le site Redmond mais désactiver le transfert d’appel de connecteur de données pour le site de Dublin, comme illustré dans l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="5ab47-145">For example, an administrator can enable Call Data Connector forwarding for the Redmond site but disable Call Data Connector forwarding for the Dublin site, as shown in the following example:</span></span>
  
```
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

<span data-ttu-id="5ab47-146">(Les paramètres configurés au niveau du site sont prioritaires sur les paramètres configurés au niveau global.)</span><span class="sxs-lookup"><span data-stu-id="5ab47-146">Settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="5ab47-147">Par exemple, supposons que le transfert d’appel de connecteur de données est activée dans l’étendue globale, mais désactivé au niveau du site (pour le site de Redmond).</span><span class="sxs-lookup"><span data-stu-id="5ab47-147">For example, suppose Call Data Connector forwarding is enabled at the global scope, but disabled at the site scope (for the Redmond site).</span></span> <span data-ttu-id="5ab47-148">Ce qui signifie que les appels enregistrement des détails et informations QoE n’est pas transférés pour les utilisateurs du site de Redmond.</span><span class="sxs-lookup"><span data-stu-id="5ab47-148">That means that call detail recording and QoE information will not be forwarded for users in the Redmond site.</span></span> <span data-ttu-id="5ab47-149">Cependant, les utilisateurs d’autres sites (autrement dit, les utilisateurs gérés par les paramètres globaux plutôt que les paramètres du site Redmond) auront leur enregistrement des détails des appels et les informations QoE transféré.</span><span class="sxs-lookup"><span data-stu-id="5ab47-149">However, users in other sites (that is, users managed by the global settings instead of the Redmond site settings) will have their call detail recording and QoE information forwarded.</span></span>

<span data-ttu-id="5ab47-150">Valeurs pour les paramètres fréquemment utilisés par le connecteur de données d’appel sont indiqués dans le tableau suivant :</span><span class="sxs-lookup"><span data-stu-id="5ab47-150">Values for the most commonly used settings used by Call Data Connector are shown in the following table:</span></span>  
|<span data-ttu-id="5ab47-151">Propriété</span><span class="sxs-lookup"><span data-stu-id="5ab47-151">Property</span></span>|<span data-ttu-id="5ab47-152">Description</span><span class="sxs-lookup"><span data-stu-id="5ab47-152">Description</span></span>|<span data-ttu-id="5ab47-153">Valeur par défaut</span><span class="sxs-lookup"><span data-stu-id="5ab47-153">Default value</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5ab47-154">EnableCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="5ab47-154">EnableCallDataConnector</span></span>  <br/> |<span data-ttu-id="5ab47-155">Indique si le connecteur de données d’appel est activée.</span><span class="sxs-lookup"><span data-stu-id="5ab47-155">Indicates whether Call Data Connector is enabled.</span></span> <span data-ttu-id="5ab47-156">Si True, surveillance des enregistrements est transféré à l’analyse en ligne.</span><span class="sxs-lookup"><span data-stu-id="5ab47-156">If True, monitoring records will be forwarded to online monitoring.</span></span>  <br/> |<span data-ttu-id="5ab47-157">$False</span><span class="sxs-lookup"><span data-stu-id="5ab47-157">$False</span></span>  <br/> |
| <span data-ttu-id="5ab47-158">Identity </span><span class="sxs-lookup"><span data-stu-id="5ab47-158">Identity</span></span> | <span data-ttu-id="5ab47-159">Détermine le niveau de l’étendue de la commande : global ou site.</span><span class="sxs-lookup"><span data-stu-id="5ab47-159">Determines the scope level for the command: global or site.</span></span>   | <span data-ttu-id="5ab47-160">global</span><span class="sxs-lookup"><span data-stu-id="5ab47-160">global</span></span>  |

## <a name="disable-call-data-connector"></a><span data-ttu-id="5ab47-161">Désactiver le connecteur de données d’appel</span><span class="sxs-lookup"><span data-stu-id="5ab47-161">Disable Call Data Connector</span></span>

<span data-ttu-id="5ab47-162">Désactivation de connecteur de données d’appel dissocier pas au magasin d’analyse à partir du pool frontal, ni ne désinstaller affecter la base de données de surveillance de serveur principal.</span><span class="sxs-lookup"><span data-stu-id="5ab47-162">Disabling Call Data Connector does not disassociate the monitoring store from the Front End pool, nor does it uninstall or otherwise affect the backend monitoring database.</span></span> <span data-ttu-id="5ab47-163">Lorsque vous désactivez le connecteur de données d’appel, vous arrêtez Skype pour Business Server à partir du téléchargement de données de l’appel vers le nuage.</span><span class="sxs-lookup"><span data-stu-id="5ab47-163">When you disable Call Data Connector, you stop Skype for Business Server from uploading call data to the cloud.</span></span> 

<span data-ttu-id="5ab47-164">Vous désactivez appeler un connecteur de données à l’aide de l’applet de commande Set-CsCloudCallDataConnectorConfiguration à partir de la Skype pour shell de gestion Business Server.</span><span class="sxs-lookup"><span data-stu-id="5ab47-164">You disable Call Data Connector by using the Set-CsCloudCallDataConnectorConfiguration cmdlet from within the Skype for Business Server management shell.</span></span> <span data-ttu-id="5ab47-165">Par exemple, la commande suivante désactive le connecteur de données d’appel dans l’étendue globale en définissant la propriété EnableCallDataConnector sur $False :</span><span class="sxs-lookup"><span data-stu-id="5ab47-165">For example, the following command disables Call Data Connector at the global scope by setting the EnableCallDataConnector property to $False:</span></span>
  
```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

<span data-ttu-id="5ab47-166">Si vous souhaitez reprendre le téléchargement des données d’appel vers le nuage, définissez la propriété EnableCallDataConnector sur $True, comme illustré dans l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="5ab47-166">If you want to resume uploading call data to the cloud, set the EnableCallDataConnector property back to $True, as shown in the following example:</span></span>

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a><span data-ttu-id="5ab47-167">Affichage de données via le tableau de bord en ligne sur site</span><span class="sxs-lookup"><span data-stu-id="5ab47-167">View on-premises data through the online dashboard</span></span>

 <span data-ttu-id="5ab47-168">Une fois que le connecteur de données d’appel est activé, vous pouvez afficher vos données d’appel local sur le tableau de bord Analytique appel comme décrit dans [Utilisation appeler Analytique pour résoudre les problèmes de qualité médiocre](https://docs.microsoft.com/en-us/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality).</span><span class="sxs-lookup"><span data-stu-id="5ab47-168">After Call Data Connector is enabled, you can view your on-premises call data on the Call Analytics dashboard as described in  [Use Call Analytics to troubleshoot poor quality](https://docs.microsoft.com/en-us/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality).</span></span>


## <a name="for-more-information"></a><span data-ttu-id="5ab47-169">Pour plus d'informations</span><span class="sxs-lookup"><span data-stu-id="5ab47-169">For more information</span></span>

<span data-ttu-id="5ab47-170">Pour plus d’informations sur les applets de commande, vous pouvez utiliser la commande Get-Help le Skype pour Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="5ab47-170">For more information on the cmdlets, you can use the Get-Help command from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="5ab47-171">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="5ab47-171">For example:</span></span>
  
<span data-ttu-id="5ab47-172">Get-Help Get-CsCloudCallDataConnector | plus</span><span class="sxs-lookup"><span data-stu-id="5ab47-172">Get-Help Get-CsCloudCallDataConnector | more</span></span>

<span data-ttu-id="5ab47-173">Get-Help Set-CsCloudCallDataConnector | plus</span><span class="sxs-lookup"><span data-stu-id="5ab47-173">Get-Help Set-CsCloudCallDataConnector | more</span></span>

<span data-ttu-id="5ab47-174">Get-Help Set-CsCloudCallDataConnectorConfiguration | plus</span><span class="sxs-lookup"><span data-stu-id="5ab47-174">Get-Help Set-CsCloudCallDataConnectorConfiguration | more</span></span>