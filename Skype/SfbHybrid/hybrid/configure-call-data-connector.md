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
description: Instructions de configuration du connecteur de données d’appel, qui permet d’afficher la télémétrie à partir de Skype Entreprise localement à l’aide des outils Skype Entreprise Online.
ms.openlocfilehash: 0d92d31798cd4b3fb5a1b4c555ff0ff00c2bdf31
ms.sourcegitcommit: 07761c26b53d92fc36b82cab7b3e38a6de4ff945
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/02/2022
ms.locfileid: "67156932"
---
# <a name="configure-call-data-connector"></a>Configurer le connecteur de données d’appel

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


Cet article explique comment configurer Call Data Connector, un ensemble d’outils unique qui permet d’afficher Skype Entreprise Server données de qualité des appels à l’aide des outils CQD (Microsoft Call Quality Dashboard) et Call Analytics (CA).

Pour plus d’informations sur les avantages et les prérequis du connecteur de données d’appel, tels que les exigences de rôle et la configuration de la connectivité hybride, consultez [Plan Call Data Connector](plan-call-data-connector.md).

## <a name="enable-monitoring"></a>Activer la surveillance
 
Vous devez configurer l’enregistrement des données d’appel (CDR) et la collecte de données de qualité d’expérience (QoE) dans votre supervision de pool frontal avec des bases de données LCSCdr et QoEMetrics locales ; sinon, les tableaux de bord Analyse des appels et Qualité des appels n’obtiendront pas de données à utiliser. Avant de configurer Call Data Connector, suivez les étapes fournies dans [Déployer la surveillance dans Skype Entreprise Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) pour configurer CDR et QoE, ainsi que la supervision de base.

> [!IMPORTANT]
> Le connecteur de données d’appel ne fonctionnera pas si l’analyse n’est pas activée sur le pool frontal.

## <a name="enable-call-data-connector"></a>Activer le connecteur de données d’appel

Pour configurer et activer Call Data Connector, vous allez utiliser les applets de commande suivantes :

| Applet de commande| Description|
| :-----------------|---------------:|
| New-CsCloudCallDataConnection | Applet de commande en ligne qui établit un collecteur de données en ligne.|
| Get-CsCloudCallDataConnection | Applet de commande en ligne qui récupère un collecteur de données en ligne existant.|  
| Get-CsCloudCallDataConnector | Applet de commande locale qui récupère les informations de connexion créées par l’applet de commande New-CsCloudCallDataConnection. |
| Set-CsCloudCallDataConnector | Applet de commande locale qui enregistre une copie locale des informations de connexion créées par l’applet de commande New-CsCloudCallDataConnection. |  
| Set-CsCloudCallDataConnectorConfiguration | Applet de commande locale qui vous permet d’activer ou de désactiver le connecteur et de personnaliser le niveau d’étendue.|

> [!NOTE]
> Pour effacer votre configuration et recommencer, utilisez l’applet de commande Remove-csclouddatconnectorconfiguration.

### <a name="configure-your-environment"></a>Configurer votre environnement 

Pour configurer votre environnement afin d’activer un collecteur de données en ligne, vous devez d’abord vous connecter au module Microsoft Teams PowerShell en tant qu’administrateur. Pour plus d’informations, consultez [la vue d’ensemble de Microsoft Teams PowerShell](/microsoftteams/teams-powershell-overview).

Il existe deux méthodes pour se connecter au module Microsoft Teams PowerShell :

- À partir de l’interpréteur de commandes de gestion Skype Entreprise Server 2019 (méthode recommandée)
- À partir d’une autre session PowerShell

#### <a name="log-in-to-microsoft-teams-powershell-module-from-the-skype-for-business-server-management-shell-recommended-method"></a>Connectez-vous au module Microsoft Teams PowerShell à partir de l’interpréteur de commandes de gestion Skype Entreprise Server (méthode recommandée)

1. Si vous activez le connecteur pour la première fois, exécutez la commande suivante :

   ```PowerShell
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. Si vous obtenez une erreur indiquant que la connexion existe déjà, cela signifie que la connexion de données d’appel existe déjà pour votre locataire. Dans ce cas, exécutez la commande : 

   ```PowerShell
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-microsoft-teams-powershell-module-from-another-powershell-session-optional-method"></a>Connectez-vous au module Microsoft Teams PowerShell à partir d’une autre session PowerShell (méthode facultative)

1.  Si vous activez le connecteur pour la première fois, exécutez la commande suivante : 

    ```PowerShell 
    New-CsCloudCallDataConnection 
    ```

2.  Si vous obtenez une erreur indiquant que la connexion existe déjà, cela signifie que la connexion de données d’appel existe déjà pour votre locataire. Dans ce cas, exécutez la commande : 

    ```PowerShell
    Get-CsCloudCallDataConnection  
    ```

La sortie des commandes ci-dessus contient une valeur de jeton dont vous aurez besoin lors de la configuration de votre environnement local comme suit :

Dans l’interpréteur de commandes de gestion Skype Entreprise Server, spécifiez la commande suivante :

```PowerShell
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a>Configurer l'étendue

Vous pouvez activer Call Data Connector pour un site particulier ou pour l’ensemble de votre déploiement Skype Entreprise Server à l’aide de l’applet de commande Set-CsCloudCallDataConnectorConfiguration à partir de l’interpréteur de commandes de gestion Skype Entreprise Server. Par exemple, la commande suivante active Call Data Connector à l’étendue globale :

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

En plus des paramètres globaux, les paramètres de configuration du connecteur de données d’appel peuvent être affectés à l’étendue du site. Cela offre une flexibilité de gestion supplémentaire en matière de surveillance. Par exemple, un administrateur peut activer le transfert du connecteur de données d’appel pour le site Redmond, mais désactiver le transfert du connecteur de données d’appel pour le site de Dublin, comme illustré dans l’exemple suivant :

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

(Les paramètres configurés au niveau du site sont prioritaires sur les paramètres configurés au niveau global.) Par exemple, supposons que le transfert du connecteur de données d’appel est activé au niveau de l’étendue globale, mais désactivé dans l’étendue du site (pour le site de Redmond). Cela signifie que l’enregistrement des détails des appels et les informations de QoE ne seront pas transférés pour les utilisateurs sur le site de Redmond. Toutefois, les utilisateurs d’autres sites (c’est-à-dire les utilisateurs gérés par les paramètres globaux au lieu des paramètres du site Redmond) verront leur enregistrement des détails d’appel et les informations QoE transférées.

Les valeurs des paramètres les plus couramment utilisés par Call Data Connector sont affichées dans le tableau suivant :  

|Propriété|Description|Valeur par défaut|
|:-----|:-----|:-----|
|EnableCallDataConnector  <br/> |Indique si le connecteur de données d’appel est activé. Si la valeur est True, les enregistrements de surveillance sont transférés à la surveillance en ligne.  <br/> |$False  <br/> |
| Identité | Détermine le niveau d’étendue de la commande : global ou site.   | global  |

## <a name="disable-call-data-connector"></a>Désactiver le connecteur de données d’appel

La désactivation du connecteur de données d’appel ne dissocie pas le magasin d’analyse du pool frontal, ni ne désinstalle ou n’affecte pas la base de données de surveillance principale. Lorsque vous désactivez Call Data Connector, vous arrêtez Skype Entreprise Server de charger des données d’appel dans le cloud. 

Vous désactivez Call Data Connector à l’aide de l’applet de commande Set-CsCloudCallDataConnectorConfiguration à partir de l’interpréteur de commandes de gestion Skype Entreprise Server. Par exemple, la commande suivante désactive Call Data Connector à l’étendue globale en définissant la propriété EnableCallDataConnector sur $False :

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

Si vous souhaitez reprendre le chargement des données d’appel dans le cloud, définissez la propriété EnableCallDataConnector sur $True, comme indiqué dans l’exemple suivant :

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a>Afficher des données locales via le tableau de bord en ligne

 Une fois le connecteur de données d’appel activé, vous pouvez afficher vos données d’appel locales dans le tableau de bord Analyse des appels ou Tableau de bord de qualité des appels, comme décrit dans [Utiliser l’analytique des appels pour résoudre les problèmes de mauvaise qualité](/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality) et [activer et utiliser le tableau de bord qualité des appels pour Microsoft Teams et Skype Entreprise Online](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard).

## <a name="for-more-information"></a>Pour plus d'informations

Pour plus d’informations sur les applets de commande, vous pouvez utiliser la commande Get-Help à partir de l’interpréteur de commandes Skype Entreprise Server Management Shell. Par exemple :

Get-Help Get-CsCloudCallDataConnector | plus

Get-Help Set-CsCloudCallDataConnector | plus

Get-Help Set-CsCloudCallDataConnectorConfiguration | plus
