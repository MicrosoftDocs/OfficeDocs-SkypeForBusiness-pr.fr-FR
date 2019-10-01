---
title: Configurer le connecteur de données d’appel
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Instructions pour la configuration du connecteur de données d’appel, qui permet d’afficher la télémétrie à partir de Skype entreprise en local à l’aide des outils Skype entreprise online.
ms.openlocfilehash: 48af644523e9872107c814aa330d2af2d9a4272f
ms.sourcegitcommit: 1f84b0edc4e418259b9f6392370e2cc4dc70df82
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2019
ms.locfileid: "37328373"
---
# <a name="configure-call-data-connector"></a>Configurer le connecteur de données d’appel

Cet article explique comment configurer le connecteur de données d’appel, un seul ensemble d’outils qui permet d’afficher les données de qualité des appels de Skype entreprise Server à l’aide des outils de tableau de bord de qualité des appels de Skype entreprise Online (CQD) et des outils d’analyse des appels.

Pour plus d’informations sur les avantages et les conditions préalables du connecteur de données d’appel, tels que les exigences de rôle et la configuration de la connectivité hybride, voir [plan Call Data Connector](plan-call-data-connector.md).

## <a name="enable-monitoring"></a>Activer la surveillance
 
Vous devez configurer la collecte de données d’enregistrement des données d’appels (CDR) et de qualité de l’expérience (QoE) dans votre surveillance de pool frontal, avec des bases de données LCSCdr et QoEMetrics locales ; dans le cas contraire, les tableaux de bord d’analyse de l’appel et de qualité des appels n’obtiendront pas de données à utiliser. Avant de configurer le connecteur de données d’appel, suivez les étapes décrites dans [Deploy Monitoring in Skype for Business Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) pour configurer à la fois les enregistrements CDR et QoE, ainsi que la surveillance de base.

> [!IMPORTANT]
> Le connecteur de données d’appel ne fonctionne pas si la surveillance n’est pas activée sur le pool frontal.

## <a name="enable-call-data-connector"></a>Activer le connecteur de données d’appel

Pour configurer et activer le connecteur de données d’appel, vous devez utiliser les applets de commande suivantes :

| Applet de commande| Description|
| :-----------------|---------------:|
| New-CsCloudCallDataConnection | Cmdlet en ligne qui établit un collecteur de données en ligne.|
| Get-CsCloudCallDataConnection | Cmdlet en ligne qui récupère un collecteur de données en ligne existant.|  
| Get-CsCloudCallDataConnector | Une cmdlet locale qui récupère les informations de connexion créées par la cmdlet New-CsCloudCallDataConnection. |
| Set-CsCloudCallDataConnector | Une applet de commande locale qui enregistre une copie locale des informations de connexion créées par la cmdlet New-CsCloudCallDataConnection. |  
| Set-CsCloudCallDataConnectorConfiguration | Une applet de commande locale qui vous permet d’activer ou de désactiver le connecteur et de personnaliser le niveau d’étendue.|

> [!NOTE]
> Pour effacer votre configuration et recommencer, utilisez la cmdlet Remove-csclouddatconnectorconfiguration.

### <a name="configure-your-environment"></a>Configurer votre environnement 

Pour configurer votre environnement afin d’activer un collecteur de données en ligne, vous devez d’abord vous connecter à Skype entreprise Online PowerShell en tant qu’administrateur. Pour plus d’informations, reportez-vous à la rubrique [Manage Skype for Business Online with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

Il existe deux méthodes pour vous connecter à Skype entreprise Online PowerShell :

- À partir de Skype entreprise Server 2019 Management Shell (méthode recommandée)
- À partir d’une autre session PowerShell

#### <a name="log-in-to-skype-for-business-online-powershell-from-the-skype-for-business-server-management-shell-recommended-method"></a>Connectez-vous à Skype entreprise Online PowerShell à partir de Skype entreprise Server Management Shell (méthode recommandée).

1. Si vous activez le connecteur pour la première fois, exécutez la commande suivante :

   ```
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. Si vous obtenez une erreur indiquant que la connexion existe déjà, cela signifie que la connexion de données d’appel existe déjà pour votre client. Dans ce cas, exécutez la commande suivante : 

   ```
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-skype-for-business-online-powershell-from-another-powershell-session-optional-method"></a>Se connecter à Skype entreprise Online PowerShell à partir d’une autre session PowerShell (méthode facultative)

1.  Si vous activez le connecteur pour la première fois, exécutez la commande suivante : 

    ``` 
    New-CsCloudCallDataConnection 
    ```

2.  Si vous obtenez une erreur indiquant que la connexion existe déjà, cela signifie que la connexion de données d’appel existe déjà pour votre client. Dans ce cas, exécutez la commande suivante : 

    ```
    Get-CsCloudCallDataConnection  
    ```

La sortie des commandes ci-dessus contient une valeur de jeton, dont vous aurez besoin lors de la configuration de votre environnement local comme suit :

À partir de Skype entreprise Server Management Shell, spécifiez la commande suivante :

```
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a>Configurer l’étendue

Vous pouvez activer le connecteur de données d’appel pour un site particulier ou pour votre déploiement de Skype entreprise Server entier à l’aide de la cmdlet Set-CsCloudCallDataConnectorConfiguration à partir de Skype entreprise Server Management Shell. Par exemple, la commande suivante active le connecteur de données d’appel au niveau global :

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

En plus des paramètres globaux, les paramètres de configuration du connecteur de données d’appel peuvent être affectés à l’étendue site. Cela offre davantage de souplesse de gestion en matière de surveillance. Par exemple, un administrateur peut activer le transfert du connecteur de données d’appel pour le site de Redmond, mais désactiver le transfert du connecteur de données d’appel pour le site Dublin, comme illustré dans l’exemple suivant :

```
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

(Les paramètres configurés au niveau du site sont prioritaires sur les paramètres configurés au niveau global.) Par exemple, supposons que le transfert du connecteur de données d’appel est activé au niveau de l’étendue globale, mais désactivé au niveau de l’étendue du site (pour le site Redmond). Cela signifie que l’enregistrement des détails des appels et les informations QoE ne seront pas transférés pour les utilisateurs du site Redmond. Toutefois, les utilisateurs d’autres sites (c’est-à-dire, les utilisateurs gérés par les paramètres globaux au lieu des paramètres du site de Redmond) disposeront de l’enregistrement des détails des appels et des informations QoE transmises.

Les valeurs des paramètres les plus fréquemment utilisés utilisés par le connecteur de données d’appel sont indiquées dans le tableau suivant :  

|Propriété|Description|Valeur par défaut|
|:-----|:-----|:-----|
|EnableCallDataConnector  <br/> |Indique si le connecteur de données d’appel est activé. Si la valeur est true, les enregistrements de surveillance sont transférés vers la surveillance en ligne.  <br/> |$False  <br/> |
| Identité | Détermine le niveau d’étendue de la commande : global ou site.   | Global  |

## <a name="disable-call-data-connector"></a>Désactiver le connecteur de données d’appel

La désactivation du connecteur de données d’appel ne dissocie pas le magasin de surveillance du pool frontal et ne désinstalle pas ou n’affecte pas la base de données de surveillance principale. Lorsque vous désactivez le connecteur de données d’appel, vous empêchez Skype entreprise Server de télécharger des données d’appel vers le Cloud. 

Vous désactivez le connecteur de données d’appel à l’aide de la cmdlet Set-CsCloudCallDataConnectorConfiguration à partir de Skype entreprise Server Management Shell. Par exemple, la commande suivante désactive le connecteur de données d’appel au niveau de l’étendue globale en définissant la propriété EnableCallDataConnector sur $False :

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

Si vous souhaitez reprendre le téléchargement des données d’appel vers le Cloud, redéfinissez la propriété EnableCallDataConnector sur $True, comme illustré dans l’exemple suivant :

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a>Afficher les données locales via le tableau de bord en ligne

 Une fois que le connecteur de données d’appel est activé, vous pouvez afficher vos données d’appel locales dans le tableau de bord analyse des appels ou qualité des appels, comme décrit dans [utiliser l’analyse des appels pour résoudre les problèmes de qualité médiocre](https://docs.microsoft.com/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality) et [activer et utiliser le tableau de bord de qualité des appels pour Microsoft teams et Skype entreprise Online](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard).

## <a name="for-more-information"></a>Pour plus d’informations

Pour plus d’informations sur les cmdlets, vous pouvez utiliser la commande Get-Help à partir de Skype entreprise Server Management Shell. Par exemple :

Get-Help Get-CsCloudCallDataConnector | plus d'

Get-Help Set-CsCloudCallDataConnector | plus d'

Get-Help Set-CsCloudCallDataConnectorConfiguration | plus d'
