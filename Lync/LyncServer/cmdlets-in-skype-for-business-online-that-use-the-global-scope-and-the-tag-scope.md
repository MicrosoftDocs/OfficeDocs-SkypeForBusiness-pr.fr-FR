---
title: Applets de commande utilisant l’étendue globale et l’étendue de balise
TOCTitle: Applets de commande utilisant l’étendue globale et l’étendue de balise
ms:assetid: 1e2bc055-8a72-425e-967b-e253add7018c
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Dn362774(v=OCS.15)
ms:contentKeyID: 56269569
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Applets de commande utilisant l’étendue globale et l’étendue de balise

 

_**Dernière rubrique modifiée :** 2015-06-22_

Dans Skype Entreprise Online, les stratégies peuvent être configurées au niveau de l’*étendue globale* ou de l’*étendue de balise* (ou *étendue utilisateur*). Lorsque vous utilisez les applets de commande **Get-Cs**, vous n’avez pas besoin de spécifier une étendue ou une identité. Si vous appelez une de ces applets de commande sans paramètre, tous les éléments pertinents sont retournés. Par exemple, cette commande retourne des informations sur toutes vos stratégies d’accès externes :

    Get-CsExternalAccessPolicy

Vous devez seulement inclure le paramètre Identity ou Filter si vous voulez limiter les données retournées. Par exemple, pour retourner uniquement la stratégie globale, utilisez la commande suivante :

    Get-CsExternalAccessPolicy -Identity "global"

Pour retourner une stratégie utilisateur avec l’identité « RedmondAccessPolicy », utilisez la commande suivante :

    Get-CsExternalAccessPolicy -Identity "RedmondAccessPolicy"

> [!NOTE]  
> Lorsque vous référencez une stratégie utilisateur, le <strong>préfixe</strong> de balise est facultatif. Cette syntaxe, qui inclut le préfixe, est également valide :<br />
Get-CsExternalAccessPolicy –Identity &quot;tag:RedmondAccessPolicy&quot;

Pour retourner toutes les stratégies à l’exception des stratégies globales (soit toutes les stratégies utilisateur), utilisez la commande suivante :

    Get-CsExternalAccessPolicy -Filter "tag:*"

Les applets de commande suivantes sont appliquées à l’étendue globale et à l’étendue utilisateur (balise) :

  - [Get-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsClientPolicy)

  - [Get-CsConferencingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsConferencingPolicy)

  - [Get-CsDialPlan](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsDialPlan)

  - [Get-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsExternalAccessPolicy)

  - [Get-CsHostedVoicemailPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsHostedVoicemailPolicy)

  - [Get-CsPresencePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsPresencePolicy)

  - [Get-CsVoicePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsVoicePolicy)

> [!NOTE]  
> Malgré leur nom, les plans de numérotation sont des stratégies d’un point de vue fonctionnel. Le terme <em>plan de numérotation</em> est utilisé à la place de règle de numérotation par exemple, afin de conserver la terminologie utilisée dans les versions précédentes de Lync Server.

## Voir aussi

#### Concepts

[Identités, étendues et clients](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Applets de commande de Lync Online](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

