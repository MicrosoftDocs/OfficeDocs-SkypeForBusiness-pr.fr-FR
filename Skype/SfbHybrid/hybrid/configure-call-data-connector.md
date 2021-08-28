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
ms.localizationpriority: medium
ms.collection: ''
description: Instructions de configuration du connecteur de données d’appel, qui permet d’afficher la télémétrie à partir Skype Entreprise sur site à l’aide des outils Skype Entreprise Online.
ms.openlocfilehash: 0e064e26ce7b8bfb97793666808b0b8a88ab2efc
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58581148"
---
# <a name="configure-call-data-connector"></a>Configurer le connecteur de données d’appel

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


Cet article explique comment configurer Le connecteur de données d’appel, un ensemble d’outils unique qui permet d’afficher les données de qualité des appels Skype Entreprise Server à l’aide des outils de tableau de bord de qualité des appels (CQD) et d’analyse des appels (CA) Skype Entreprise Online.

Pour plus d’informations sur les avantages et les conditions préalables du connecteur de données d’appel, telles que les exigences de rôle et la configuration de la connectivité hybride, voir [Plan Call Data Connector](plan-call-data-connector.md).

## <a name="enable-monitoring"></a>Activer la surveillance
 
Vous devez configurer l’enregistrement des données des appels (CDR) et la collecte de données de qualité de l’expérience (QoE) dans la surveillance de votre pool frontal, avec des bases de données LCSCdr et QoEMetrics locales. Dans le cas contraire, les tableaux de bord d’analyse des appels et de qualité des appels n’auront pas de données à travailler. Avant de configurer le connecteur de données d’appel, suivez les étapes fournies dans Déployer la surveillance dans [Skype Entreprise Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) pour configurer l’cdr et QoE, ainsi que la surveillance de base.

> [!IMPORTANT]
> Le connecteur de données d’appel ne fonctionne pas si la surveillance n’est pas activée sur le pool frontal.

## <a name="enable-call-data-connector"></a>Activer le connecteur de données d’appel

Pour configurer et activer le connecteur de données d’appel, vous utiliserez les cmdlets suivantes :

| Applet de commande| Description|
| :-----------------|---------------:|
| New-CsCloudCallDataConnection | Cmdlet en ligne qui établit un collecteur de données en ligne.|
| Get-CsCloudCallDataConnection | Cmdlet en ligne qui récupère un collecteur de données en ligne existant.|  
| Get-CsCloudCallDataConnector | Cmdlet sur site qui récupère les informations de connexion créées par l'New-CsCloudCallDataConnection cmdlet. |
| Set-CsCloudCallDataConnector | Cmdlet sur site qui enregistre une copie sur site des informations de connexion créées par l'New-CsCloudCallDataConnection cmdlet. |  
| Set-CsCloudCallDataConnectorConfiguration | Une cmdlet sur site qui vous permet d’activer ou de désactiver le connecteur et de personnaliser le niveau d’étendue.|

> [!NOTE]
> Pour effacer votre configuration et recommencer, utilisez l’cmdlet Remove-csclouddatconnectorconfiguration.

### <a name="configure-your-environment"></a>Configurer votre environnement 

Pour configurer votre environnement afin d’activer un collecteur de données en ligne, vous devez d’abord vous connecter à Skype Entreprise Online PowerShell en tant qu’administrateur. Pour plus d’informations, [voir Gérer Skype Entreprise Online avec Office 365 PowerShell.](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)

Il existe deux méthodes pour vous connecter à Skype Entreprise Online PowerShell :

- À partir Skype Entreprise Server 2019 Management Shell (méthode recommandée)
- À partir d’une autre session PowerShell

#### <a name="log-in-to-skype-for-business-online-powershell-from-the-skype-for-business-server-management-shell-recommended-method"></a>Connectez-vous Skype Entreprise Online PowerShell à partir de l’Skype Entreprise Server management shell (méthode recommandée)

1. Si vous activez le connecteur pour la première fois, exécutez la commande suivante :

   ```PowerShell
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. Si vous obtenez une erreur qui indique que la connexion existe déjà, cela signifie que la connexion de données d’appel existe déjà pour votre client. Dans ce cas, exécutez la commande : 

   ```PowerShell
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-skype-for-business-online-powershell-from-another-powershell-session-optional-method"></a>Connectez-vous Skype Entreprise Online PowerShell à partir d’une autre session PowerShell (méthode facultative)

1.  Si vous activez le connecteur pour la première fois, exécutez la commande suivante : 

    ```PowerShell 
    New-CsCloudCallDataConnection 
    ```

2.  Si vous obtenez une erreur qui indique que la connexion existe déjà, cela signifie que la connexion de données d’appel existe déjà pour votre client. Dans ce cas, exécutez la commande : 

    ```PowerShell
    Get-CsCloudCallDataConnection  
    ```

La sortie des commandes ci-dessus contient une valeur de jeton, dont vous aurez besoin lors de la configuration de votre environnement local comme suit :

Dans l’Skype Entreprise Server de gestion, spécifiez la commande suivante :

```PowerShell
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a>Configurer l’étendue

Vous pouvez activer le connecteur de données d’appel pour un site particulier ou pour l’ensemble de votre déploiement Skype Entreprise Server à l’aide de la cmdlet Set-CsCloudCallDataConnectorConfiguration à partir de l’Skype Entreprise Server de gestion. Par exemple, la commande suivante active Le connecteur de données d’appel au niveau de l’étendue globale :

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

Outre les paramètres globaux, les paramètres de configuration du connecteur de données d’appel peuvent être affectés à l’étendue Site. Cela offre une flexibilité de gestion supplémentaire en matière de surveillance. Par exemple, un administrateur peut activer le connecteur de données d’appel pour le site Redmond, mais désactiver le forwarding call data connector pour le site Dublin, comme illustré dans l’exemple suivant :

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

(Les paramètres configurés au niveau du site sont prioritaires sur les paramètres configurés au niveau global.) Par exemple, supposons que le connecteur de données d’appel soit activé au niveau de l’étendue globale, mais désactivé au niveau de l’étendue Site (pour le site redmond). Cela signifie que l’enregistrement des détails des appels et les informations QoE ne seront pas transmis aux utilisateurs du site redmond. Toutefois, les utilisateurs d’autres sites (c’est-à-dire, les utilisateurs gérés par les paramètres globaux au lieu des paramètres du site de Redmond) auront leur enregistrement des détails des appels et les informations QoE sont transmis.

Les valeurs des paramètres les plus couramment utilisés par le connecteur de données d’appel sont indiquées dans le tableau suivant :  

|Propriété|Description|Valeur par défaut|
|:-----|:-----|:-----|
|EnableCallDataConnector  <br/> |Indique si le connecteur de données d’appel est activé. Si la valeur est True, les enregistrements de surveillance sont transmis à la surveillance en ligne.  <br/> |$False  <br/> |
| Identité | Détermine le niveau d’étendue de la commande : global ou site.   | global  |

## <a name="disable-call-data-connector"></a>Désactiver le connecteur de données d’appel

La désactivation du connecteur de données d’appel ne dissocie pas le magasin d’analyse du pool frontal, ni ne désinstalle ni n’affecte la base de données de surveillance principale. Lorsque vous désactivez le connecteur de données d’appel, vous empêchez Skype Entreprise Server de télécharger des données d’appel dans le cloud. 

Vous désactivez le connecteur de données d’appel à l’aide Set-CsCloudCallDataConnectorConfiguration cmdlet à partir de l’Skype Entreprise Server de gestion. Par exemple, la commande suivante désactive le connecteur de données d’appel au niveau de l’étendue globale en activant la propriété EnableCallDataConnector sur $False :

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

Si vous souhaitez reprendre le téléchargement des données d’appel vers le cloud, rétablissez la propriété EnableCallDataConnector sur $True, comme illustré dans l’exemple suivant :

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a>Afficher les données sur site via le tableau de bord en ligne

 Une fois le connecteur de données d’appel activé, vous pouvez afficher vos données d’appel sur site dans le tableau de bord d’analyse des appels ou le tableau de bord de qualité des appels, comme décrit dans l’analyse des appels pour résoudre les problèmes de qualité médiocre et activer et utiliser le tableau de bord de qualité des appels pour Microsoft Teams et [Skype Entreprise Online.](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard) [](/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality)

## <a name="for-more-information"></a>Pour plus d'informations

Pour plus d’informations sur les cmdlets, vous pouvez utiliser la commande Get-Help de l’Skype Entreprise Server Management Shell. Par exemple :

Get-Help Get-CsCloudCallDataConnector | more

Get-Help Set-CsCloudCallDataConnector | more

Get-Help Set-CsCloudCallDataConnectorConfiguration | more