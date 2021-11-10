---
title: Configurer Azure AD Connecter
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
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
search.appverid: MET150
description: Instructions de configuration des Azure AD Connecter dans un environnement hybride.
ms.openlocfilehash: cfb290ecc6892001a9e20d9260c54c076a51dfe3
ms.sourcegitcommit: 11a803d569a57410e7e648f53b28df80a53337b6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/10/2021
ms.locfileid: "60887212"
---
# <a name="configure-azure-ad-connect-for-teams-and-skype-for-business"></a> Configurer Azure AD Connexion pour les Teams et Skype pour les entreprises 

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

 
Pour utiliser Teams, les organisations avec un déploiement local de Skype Entreprise Server ou Lync Server 2013 doivent configurer Azure AD Connecter pour synchroniser leur annuaire local avec Microsoft 365. Les organisations Skype Entreprise Server locales doivent s’assurer que les attributs msRTCSIP appropriés sont synchronisés dans Azure AD. Dans cet article, toute référence à « Skype Entreprise Server » s’applique également à Lync Server 2013.

> [!NOTE]
> - Pour obtenir toutes les fonctionnalités, les utilisateurs Teams existants qui ont également Skype Entreprise en local doivent avoir leur compte local Skype Entreprise déplacé vers le cloud. Par exemple, pour obtenir des fonctionnalités telles que la possibilité d’interopérer avec Skype Entreprise utilisateurs et de communiquer avec des utilisateurs d’organisations fédérées. Si l’utilisateur local utilise uniquement Teams, vous devez toujours le déplacer vers le cloud pour fournir une fonctionnalité Teams complète en tant qu’utilisateur TeamsOnly. Pour que cette migration puisse avoir lieu, vous devez configurer Azure AD Connecter afin de pouvoir activer l’hybride.
> - Si vous ne prévoyez pas de déplacer des utilisateurs de l’organisation vers le cloud à tout moment, vous devez toujours configurer Azure AD Connecter afin que les comptes Teams et Skype Entreprise Server co-existent.
 

## <a name="background-information"></a>Informations contextuelles

Azure Active Directory Connecter votre annuaire Active Directory local reste synchronisé en continu avec Microsoft 365. Votre annuaire local reste la source d’identité faisant autorité, tandis que les modifications de votre environnement local sont synchronisées Azure AD. Pour plus d’informations, [voir Azure AD Connecter Sync](/azure/active-directory/hybrid/how-to-connect-sync-whatis).  *Les utilisateurs de votre organisation seront représentés dans* vos annuaires locaux et en ligne.  Tous les utilisateurs qui utilisent Teams ou Skype Entreprise en local doivent être synchronisés en local dans Azure AD pour garantir la coexistence de ces comptes. En outre, vous pouvez faciliter la communication entre les utilisateurs locaux et en ligne via Skype Entreprise connectivité hybride, qui nécessite également la configuration de Azure AD Connecter.


## <a name="configuring-azure-ad-when-you-have-skype-for-business-server"></a>Configurer Azure AD lorsque vous avez Skype Entreprise Server 

### <a name="general-requirements"></a>Conditions requises générales 

Pour qu’un déploiement local de Skype Entreprise Server co-existe avec Teams, certains attributs Active Directory du déploiement local doivent être synchronisés dans Azure AD à l’aide de Azure AD Connecter. Le programme d Azure AD Connecter configure automatiquement les attributs requis à synchroniser par défaut lorsqu’il détecte la présence de Skype Entreprise Server dans votre environnement local. Ces attributs incluent des attributs d’identité généraux, tels que le nom d’utilisateur principal, ainsi que des attributs précédés de « msRTCSIP », qui sont spécifiques à Skype For Business Server. L’ensemble complet des attributs est répertorié à [l Azure AD Connecter sync : Attributes synchronized to Azure Active Directory](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized#teams-and-skype-for-business-online).

Si vous choisissez de personnaliser les paramètres de synchronisation dans Azure AD Connecter, vous devez vous assurer que les attributs suivants sont synchronisés pour les objets utilisateur :
</br>

|Attribut|Description|
|---|---|
|msRTCSIP-PrimaryUserAddress| Adresse SIP de l’utilisateur dans l’environnement local|
|msRTCSIP-DeploymentLocator| Indique si l’utilisateur est homed local ou dans le cloud|
|msRTCSIP-UserEnabled| Si l’utilisateur est activé pour la fonctionnalité SIP|
|||

</br>
</br>
En outre, si vous gérez les attributs du système téléphonique via votre déploiement local, vous devez également synchroniser les attributs suivants :

|Attribut|Description|
|:---|:---|
|msRTCSIP-Line| Numéro de téléphone de l’utilisateur|
|msRTCSIP-OptionFlags| Indique si l’utilisateur est activé pour les fonctionnalités vocales|
|msRTCSIP-OwnerUrn| Utilisé pour identifier les points de terminaison d’application hybride|
|||

</br>
Microsoft recommande de synchroniser toutes les forêts qui contiennent des identités d’utilisateur, ainsi que toutes les forêts qui contiennent des Skype Entreprise Server. Si les identités des utilisateurs existent dans plusieurs forêts, Azure AD Connect doit effectuer la fusion. Lorsque ces instructions sont suivies, Azure AD Connect synchronise automatiquement les attributs corrects, à condition que vous ne modifiez pas les connecteurs ou les règles de synchronisation dans Azure AD Connect. 
  
Si vous ne synchronisez pas à partir de toutes les forêts qui contiennent des identités d’utilisateur et le déploiement Skype Entreprise Server, vous devez vous assurer que les attributs d’identité et de Skype Entreprise pertinents sont correctement remplis en Azure AD pour tout utilisateur utilisant Teams ou Skype Entreprise (local ou en ligne). Cela nécessitera probablement une synchronisation d’annuaires sur site supplémentaire. Pour plus d’informations, [voir Azure AD Connecter sync: Attributes synchronized to Azure Active Directory](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized).

Il incombe au client de garantir une configuration appropriée pour remplir les attributs dans Azure AD. Gardez les éléments suivants à l’esprit : 

- L’utilisation d’une configuration non standard pour la synchronisation Azure AD est risquée. Des configurations non conformes peuvent entraîner une altération des données dans votre répertoire en ligne.

- À mesure que les produits évoluent, Microsoft continuera à vérifier les configurations de synchronisation standard dans lesquelles toutes les forêts appropriées sont synchronisées. Les clients disposant de configurations de synchronisation personnalisées sont chargés de s’assurer que leurs configurations apportent les attributs et valeurs appropriés dans Azure AD. 

Que vous utilisiez une forêt Active Directory sur site ou plusieurs forêts, Azure AD Connecter peut être utilisé dans une variété de topologies pris en charge, comme décrit dans [topologies](/azure/active-directory/hybrid/plan-connect-topologies)pour Azure AD Connecter . Du point de vue Skype Entreprise Server, il existe trois variantes : 

1. Une forêt unique, qui contient les identités utilisateur faisant autorité et héberge Skype Entreprise Server. 

2. Plusieurs forêts, dont une seule héberge Skype Entreprise Server, ainsi qu’une ou plusieurs autres forêts contenant les identités des utilisateurs faisant autorité (les forêts de comptes). 

3. Plusieurs déploiements de Skype Entreprise Server dans plusieurs forêts. Si certaines conditions sont remplies, les organisations peuvent consolider ces déploiements multiples en une seule Microsoft 365 organisation.

### <a name="single-forest"></a>Forêt unique 

Si les comptes d’utilisateur et Skype Entreprise sont hébergés dans une seule forêt, vous devez vous assurer qu’Azure AD Connect est configuré pour synchroniser les utilisateurs de cette forêt dans Azure AD.  Par défaut, les attributs appropriés sont automatiquement synchronisés dans Azure Active Directory. Il est conseillé aux clients de ne pas modifier les règles de synchronisation intégrées et/ou les connecteurs qui gèrent la configuration (ce qui n’est pas possible à partir de l’Assistant d’installation).  

### <a name="multiple-forests-with-one-skype-for-business-deployment"></a>Plusieurs forêts avec un déploiement de Skype Entreprise 

Ce scénario est souvent appelé topologie de forêt de ressources. Les identités des utilisateurs faisant autorité sont hébergées dans une ou plusieurs forêts de comptes, et Skype Entreprise est déployé dans une forêt de ressources distincte (elle-même peut également héberger les identités d’utilisateurs faisant autorité). En général, les identités des utilisateurs faisant autorité de Skype Entreprise peuvent se trouver dans la même forêt que Skype Entreprise Server et/ou dans une autre forêt, sous réserve des conditions suivantes : 

- Les utilisateurs avec des identités faisant autorité à partir des forêts de comptes sont représentés dans la forêt de ressources (où les Skype Entreprise Server sont déployés) en tant qu’objets utilisateur désactivés. L’attribut msRTCSIP-OriginatorSID de la forêt de ressources doit correspondre au SID de la forêt de comptes. Pour plus d’informations, [voir Configure a multi-forest environment for hybrid Skype Entreprise](configure-a-multi-forest-environment-for-hybrid.md).

- La forêt de ressources hébergeant Skype Entreprise Server fait confiance à la ou aux forêts de comptes.  

- Tous les objets et attributs utilisateur pertinents pour l’identité (à partir de forêts de comptes) et les Skype Entreprise (à partir de la forêt de ressources) sont synchronisés en Azure AD avec les valeurs correctes via Azure AD Connecter.  

  Pour obtenir une synchronisation correcte des objets et des attributs en Azure AD dans un scénario local à forêts [multiples,](configure-a-multi-forest-environment-for-hybrid.md)Microsoft recommande vivement d’utiliser Azure AD Connecter pour synchroniser toutes les forêts qui ont activé les comptes d’utilisateur et la forêt qui contient Skype Entreprise. Si vous procédez à une synchronisation à partir de toutes les forêts, vous devez ensuite configurer Azure AD Connect pour fusionner ces identités et les synchroniser avec Azure AD. Azure AD Connect est conçu pour prendre en charge ce scénario et offre une option intégrée dans l’Assistant d’installation pour configurer cet environnement, notamment la configuration d’ancres pour lier les identités. Choisissez les éléments suivants : Les identités des utilisateurs existent dans plusieurs **répertoires** et match à l’aide des **attributs --> ObjectSID et msExchangeMasterAccountSID**.


### <a name="multiple-skype-for-business-server-deployments-in-multiple-forests"></a>Plusieurs déploiements de Skype Entreprise Server dans plusieurs forêts 

Dans ce scénario, il existe plusieurs forêts, chacune contenant des Skype Entreprise Server et une seule Microsoft 365 organisation. Chaque forêt contenant des Skype Entreprise Server peut être synchronisée dans Azure AD pour cette organisation à l’aide de Azure AD Connecter. Au mieux, une seule forêt peut être configurée pour Skype Entreprise hybride à un moment donné. Avant d’activer l’environnement hybride dans une forêt, tous les domaines SIP de toutes les autres forêts doivent être désactivés à l’aide de [disable-csonlineSipDomain](/powershell/module/skype/disable-csonlinesipdomain). Pour plus d’informations, [voir Consolidation cloud pour Teams et Skype Entreprise](cloud-consolidation.md).


## <a name="related-information"></a>Informations connexes

- [Qu’est-ce que l’identité hybride ?](/azure/active-directory/hybrid/whatis-hybrid-identity)

- synchronisation [Azure AD Connect : comprendre et personnaliser les](/azure/active-directory/hybrid/how-to-connect-sync-whatis) de synchronisation

- [Topologies pour Azure AD Connect](/azure/active-directory/hybrid/plan-connect-topologies)

- [Azure AD Connecter synchronisation : attributs synchronisés avec Azure Active Directory](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)
