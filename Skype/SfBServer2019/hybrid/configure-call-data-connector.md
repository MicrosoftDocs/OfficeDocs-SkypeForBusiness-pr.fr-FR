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
ms.openlocfilehash: adc1c9a1e50130796c4749a958e9030c10a09fd0
ms.sourcegitcommit: 112dc19075f9213207fde9e30bcde5681324b7c9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/22/2018
ms.locfileid: "25696176"
---
# <a name="configure-call-data-connector"></a>Configurer le connecteur de données d’appel

Cet article décrit comment configurer le connecteur de données d’appel : un ensemble d’outils unique qui permet l’affichage Skype pour serveur appeler la qualité des données métiers à l’aide de Skype des outils Business Online appeler qualité du tableau de bord (CQD) et appelez Analytique (CA). 

> [!NOTE]
> Version d’évaluation, tableau de bord Analytique appeler uniquement est disponible.

Pour plus d’informations sur les avantages de l’appel de connecteur de données et les composants requis, tels que les exigences de rôle et la configuration de la connectivité hybride, voir [Planification de connecteur de données d’appel](plan-call-data-connector.md).

## <a name="enable-monitoring"></a>Activer la surveillance
 
Vous devez configurer l’enregistrement de données appels (CDR) et qualité de l’expérience (QoE) collecte des données dans votre serveur frontal du pool surveillance, locales bases de données LCSCdr et QoEMetrics ; dans le cas contraire, les tableaux de bord qualité des appels Analytique appel n’obtenir des données pour fonctionner avec. Avant que vous configurer appel données connecteur, suivez les étapes fournies dans [Deploy surveillance dans Skype pour Business Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) pour configurer à la fois des détails des appels et QoE ainsi que surveillance de base.

> [!IMPORTANT]
> Connecteur de données d’appel ne fonctionne pas si l’analyse n’est pas activé sur le pool frontal.

## <a name="enable-call-data-connector"></a>Activer le connecteur de données d’appel

Pour configurer et activer le connecteur de données d’appel, vous allez utiliser les applets de commande suivantes :

| Applet de commande| Description|
| :-----------------|---------------:|
| Nouvelle CsCloudCallDataConnection | Une applet de commande en ligne qui établit un collecteur de données en ligne.|
| Get-CsCloudCallDataConnection | Une applet de commande en ligne qui Récupère un collecteur de données en ligne existant.|  
| Get-CsCloudCallDataConnector | Applet de commande locale qui Récupère les informations de connexion créées par l’applet de commande New-CsCloudCallDataConnection. |
| Set-CsCloudCallDataConnector | Applet de commande locale qui permet d’enregistrer une copie locale, les informations de connexion créées par l’applet de commande New-CsCloudCallDataConnection. |  
| Set-CsCloudCallDataConnectorConfiguration | Applet de commande locale qui permet d’activer ou désactiver le connecteur et personnaliser le niveau de l’étendue.|

### <a name="configure-your-environment"></a>Configurer votre environnement 

Pour configurer votre environnement pour activer un collecteur de données en ligne, vous devez tout d’abord vous connecter à Skype pour Business Online PowerShell en tant qu’administrateur. Pour plus d’informations, voir [Gérer les Skype pour Business en ligne avec Office 365 PowerShell](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

Il existe deux méthodes pour la connexion à Skype pour Business Online PowerShell :

- À partir de la Skype pour Business Server 2019 management shell (méthode recommandée)
- À partir d’une autre session PowerShell

#### <a name="log-in-to-skype-for-business-online-powershell-from-the-skype-for-business-server-management-shell-recommended-method"></a>Connectez-vous à Skype pour Business Online PowerShell à partir de la Skype pour Business Server management shell (méthode recommandée)

1. Si l’activation du connector pour la première fois, exécutez la commande suivante :

   ```
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. Si vous obtenez une erreur la connexion existe déjà, cela signifie que la connexion de données déjà appel existe pour votre client. Dans ce cas, exécutez la commande : 

   ```
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-skype-for-business-online-powershell-from-another-powershell-session-optional-method"></a>Connectez-vous à Skype pour Business Online PowerShell à partir d’une autre session PowerShell (méthode facultatif)

1.  Si l’activation du connector pour la première fois, exécutez la commande suivante : 

    ``` 
    New-CsCloudCallDataConnection 
    ```

2.  Si vous obtenez une erreur la connexion existe déjà, cela signifie que la connexion de données déjà appel existe pour votre client. Dans ce cas, exécutez la commande : 

    ```
    Get-CsCloudCallDataConnection  
    ```

La sortie des commandes ci-dessus contient une valeur de jeton dont vous aurez besoin lors de la configuration de votre environnement local comme suit :

À partir de dans la Skype pour shell de gestion Business Server, spécifiez la commande suivante :

```
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a>Configurer l’étendue

Vous pouvez activer le connecteur de données d’appel pour un site particulier ou pour votre ensemble Skype pour le déploiement de serveur d’entreprise à l’aide de l’applet de commande Set-CsCloudCallDataConnectorConfiguration à partir de la Skype pour shell de gestion Business Server. Par exemple, la commande suivante permet de connecteur de données d’appel dans l’étendue globale :

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

En plus des paramètres globaux, les paramètres de configuration de connecteur de données d’appel peuvent être attribués au niveau du site. Cela offre la souplesse de gestion supplémentaires lorsqu’il s’agit de surveillance. Par exemple, un administrateur peut activer le transfert d’appel de connecteur de données pour le site Redmond mais désactiver le transfert d’appel de connecteur de données pour le site de Dublin, comme illustré dans l’exemple suivant :

```
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

(Les paramètres configurés au niveau du site sont prioritaires sur les paramètres configurés au niveau global.) Par exemple, supposons que le transfert d’appel de connecteur de données est activée dans l’étendue globale, mais désactivé au niveau du site (pour le site de Redmond). Ce qui signifie que les appels enregistrement des détails et informations QoE n’est pas transférés pour les utilisateurs du site de Redmond. Cependant, les utilisateurs d’autres sites (autrement dit, les utilisateurs gérés par les paramètres globaux plutôt que les paramètres du site Redmond) auront leur enregistrement des détails des appels et les informations QoE transféré.

Valeurs pour les paramètres fréquemment utilisés par le connecteur de données d’appel sont indiqués dans le tableau suivant :  

|Propriété|Description|Valeur par défaut|
|:-----|:-----|:-----|
|EnableCallDataConnector  <br/> |Indique si le connecteur de données d’appel est activée. Si True, surveillance des enregistrements est transféré à l’analyse en ligne.  <br/> |$False  <br/> |
| Identity  | Détermine le niveau de l’étendue de la commande : global ou site.   | global  |

## <a name="disable-call-data-connector"></a>Désactiver le connecteur de données d’appel

Désactivation de connecteur de données d’appel dissocier pas au magasin d’analyse à partir du pool frontal, ni ne désinstaller affecter la base de données de surveillance de serveur principal. Lorsque vous désactivez le connecteur de données d’appel, vous arrêtez Skype pour Business Server à partir du téléchargement de données de l’appel vers le nuage. 

Vous désactivez appeler un connecteur de données à l’aide de l’applet de commande Set-CsCloudCallDataConnectorConfiguration à partir de la Skype pour shell de gestion Business Server. Par exemple, la commande suivante désactive le connecteur de données d’appel dans l’étendue globale en définissant la propriété EnableCallDataConnector sur $False :

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

Si vous souhaitez reprendre le téléchargement des données d’appel vers le nuage, définissez la propriété EnableCallDataConnector sur $True, comme illustré dans l’exemple suivant :

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a>Affichage de données via le tableau de bord en ligne sur site

 Une fois que le connecteur de données d’appel est activé, vous pouvez afficher vos données d’appel local sur le tableau de bord Analytique appel comme décrit dans [Utilisation appeler Analytique pour résoudre les problèmes de qualité médiocre](https://docs.microsoft.com/en-us/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality).


## <a name="for-more-information"></a>Pour plus d’informations

Pour plus d’informations sur les applets de commande, vous pouvez utiliser la commande Get-Help le Skype pour Business Server Management Shell. Par exemple :

Get-Help Get-CsCloudCallDataConnector | plus

Get-Help Set-CsCloudCallDataConnector | plus

Get-Help Set-CsCloudCallDataConnectorConfiguration | plus