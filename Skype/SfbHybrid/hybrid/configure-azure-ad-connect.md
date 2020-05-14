---
title: Configurer Azure AD Connect
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
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Instructions pour la configuration d’Azure AD Connect dans un environnement hybride.
ms.openlocfilehash: 7a0c458692da1381f2ed3f52dfef8c1d360d74e2
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221468"
---
# <a name="configure-azure-ad-connect-for-teams-and-skype-for-business"></a>Configurer Azure AD Connect pour Teams et Skype Entreprise
 
Les organisations qui ont une version locale de Skype entreprise Server (ou Lync Server) et qui envisagent d’utiliser teams ou Skype entreprise Online doivent configurer Azure AD Connect pour synchroniser leur annuaire sur site avec Microsoft 365 ou Office 365, comme décrit dans ce document.  Cela inclut les organisations qui se déplacent directement de Skype entreprise en local vers Teams. En particulier les organisations disposant de Skype Entreprise en local doivent s’assurer que les attributs msRTCSIP appropriés sont synchronisés avec Azure AD. 

> [!NOTE]
> Les utilisateurs de Teams existants qui ont également Skype Entreprise en local doivent déplacer leur compte local Skype Entreprise vers le Cloud afin de pouvoir bénéficier de toutes les fonctionnalités, telles que la possibilité d’interagir avec les utilisateurs de Skype Entreprise et de communiquer avec les utilisateurs des organisations fédérées. Même si l’utilisateur n’utilise que Teams, ce compte Skype Entreprise en ligne est requis par l’infrastructure pour offrir des fonctionnalités supplémentaires.  Pour que cette migration soit effectuée, vous devez vous assurer qu’Azure AD Connect est correctement configuré de sorte que vous puissiez activer hybride.
 

## <a name="background-information"></a>Informations générales

Azure Active Directory Connect maintient votre annuaire Active Directory en permanence synchronisé avec Microsoft 365 ou Office 365.  Votre annuaire local reste la source d’identité faisant autorité et les modifications de votre environnement local sont synchronisées avec Azure AD. Pour plus d’informations, reportez-vous à la rubrique [Azure ad Connect Sync](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).  Même si vous ne déplacez pas tous les utilisateurs de l’environnement local vers le Cloud, tous les utilisateurs qui utilisent Teams, Skype entreprise en local ou Skype entreprise Online doivent être synchronisés de l’environnement local vers Azure AD pour garantir la communication entre les utilisateurs locaux et les utilisateurs en ligne. *Les utilisateurs de votre organisation seront représentés à la fois dans vos annuaires locaux et en ligne.*


## <a name="configuring-azure-ad-when-you-have-skype-for-business-server"></a>Configurer Azure AD lorsque vous avez Skype Entreprise Server 

Qu’il s’agisse d’une forêt Active Directory locale ou de plusieurs forêts, Azure AD Connect peut être utilisé dans diverses topologies prises en charge, comme décrit dans [topologies pour Azure ad Connect](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-topologies).  Du point de vue de Skype Entreprise Server, il existe trois variantes principales : 

1. Une forêt unique, qui contient les identités utilisateur faisant autorité et héberge Skype Entreprise Server. 

2. Plusieurs forêts, dont une seule héberge Skype Entreprise Server, ainsi qu’une ou plusieurs autres forêts contenant les identités des utilisateurs faisant autorité (les forêts de comptes). 

3. Plusieurs déploiements de Skype Entreprise Server dans plusieurs forêts. Sous réserve que certaines exigences soient satisfaites, les organisations peuvent consolider ces déploiements multiples en une seule organisation Microsoft 365 ou Office 365.

### <a name="single-forest"></a>Forêt unique 

Si les comptes d’utilisateur et Skype Entreprise sont hébergés dans une seule forêt, vous devez vous assurer qu’Azure AD Connect est configuré pour synchroniser les utilisateurs de cette forêt dans Azure AD.  Bien que l’Assistant Installation d’Azure AD Connect dispose de nombreuses options, les attributs appropriés sont automatiquement synchronisés avec Azure Active Directory. Les clients sont avertis de la modification des règles de synchronisation intégrées et/ou des connecteurs qui gèrent la configuration (ce qui n’est pas possible à partir de l’Assistant Installation).  

### <a name="multiple-forests-with-one-skype-for-business-deployment"></a>Plusieurs forêts avec un déploiement de Skype Entreprise 

Ce scénario est souvent appelé topologie de forêt de ressources. Les identités des utilisateurs faisant autorité sont hébergées dans une ou plusieurs forêts de comptes, et Skype Entreprise est déployé dans une forêt de ressources distincte (elle-même peut également héberger les identités d’utilisateurs faisant autorité). En général, les identités des utilisateurs faisant autorité de Skype Entreprise peuvent se trouver dans la même forêt que Skype Entreprise Server et/ou dans une autre forêt, sous réserve des conditions suivantes : 

- Les utilisateurs disposant d’identités d’autorité provenant de la ou des forêts de comptes sont représentés dans la forêt de ressources (où Skype Entreprise Server est déployé) en tant qu’objets utilisateur désactivés, et l’attribut msRTCSIP-OriginatorSID dans la forêt de ressources correspond au SID dans la forêt de comptes. Pour plus d’informations, consultez [la rubrique Configure a multi-Forest Environment for Hybrid Skype for Business](configure-a-multi-forest-environment-for-hybrid.md).

- La forêt de ressources hébergeant Skype Entreprise Server fait confiance à la ou aux forêts de comptes.  

- Tous les attributs et objets utilisateur pertinents pour l’identité (de forêts de comptes) et Skype Entreprise (de la forêt de ressources) sont synchronisés avec Azure AD avec les valeurs correctes via Azure AD Connect.  

 Pour assurer une synchronisation des attributs et des objets corrects dans Azure AD dans un [scénario local sur plusieurs forêts](configure-a-multi-forest-environment-for-hybrid.md), Microsoft recommande vivement d’utiliser Azure ad Connect pour synchroniser toutes les forêts ayant activé les comptes d’utilisateur et la forêt qui contient Skype entreprise.  Si vous procédez à une synchronisation à partir de toutes les forêts, vous devez ensuite configurer Azure AD Connect pour fusionner ces identités et les synchroniser avec Azure AD. Azure AD Connect est conçu pour prendre en charge ce scénario et offre une option intégrée dans l’Assistant d’installation pour configurer cet environnement, notamment la configuration d’ancres pour lier les identités.  Choisissez l’une des options suivantes : les identités d’utilisateur existent dans plusieurs répertoires. Associez using--> ObjectSID et les attributs msExchangeMasterAccountSID..


### <a name="multiple-skype-for-business-server-deployments-in-multiple-forests"></a>Plusieurs déploiements de Skype Entreprise Server dans plusieurs forêts 

Dans ce scénario, il existe plusieurs forêts, chacune contenant Skype entreprise Server, et une seule organisation Microsoft 365 ou Office 365.  Chaque forêt contenant Skype entreprise Server peut être synchronisée dans Azure AD pour cette organisation à l’aide d’AAD Connect. Au mieux, une seule forêt peut être configurée pour Skype Entreprise hybride à un moment donné. Avant d’activer l’environnement hybride dans une forêt, tous les domaines SIP de toutes les autres forêts doivent être désactivés à l’aide de [Disable-csonlineSipDomain](https://docs.microsoft.com/powershell/module/skype/disable-csonlinesipdomain). Pour plus d’informations sur la consolidation d’un environnement de ce type dans Microsoft 365 ou Office 365, voir [Cloud consolidation for teams and Skype for Business](cloud-consolidation.md).

## <a name="general-requirements"></a>Conditions requises générales 

Les services teams et Skype entreprise Online requièrent que les attributs Active Directory corrects existent et soient renseignés dans Azure AD.  La recommandation générale de Microsoft consiste à synchroniser toutes les forêts qui contiennent des identités d’utilisateur, ainsi que toutes les forêts qui contiennent Skype entreprise Server.

 Si les identités des utilisateurs existent dans plusieurs forêts, Azure AD Connect doit effectuer la fusion. Lorsque vous suivez ces instructions, Azure AD Connect synchronise automatiquement les attributs corrects, à condition que vous ne modifiez pas les connecteurs ou les règles de synchronisation dans Azure AD Connect. 
  
Si vous ne procédez pas à une synchronisation à partir de toutes les forêts contenant des identités d’utilisateur et le déploiement de Skype entreprise Server, vous devez toujours vous assurer que les attributs Identity et Skype for Business appropriés sont correctement renseignés dans Azure AD pour tout utilisateur qui utilise teams ou Skype entreprise (en local ou en ligne), ce qui nécessite vraisemblablement une synchronisation d’annuaires locale Pour plus d’informations, reportez-vous à la rubrique [Azure ad Connect Sync : attributs synchronisés avec Azure Active Directory](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized).

Dans ces scénarios, il incombe au client de s’assurer de la bonne configuration pour remplir les attributs dans Azure AD. Gardez les éléments suivants à l’esprit : 

- L’utilisation d’une configuration non standard pour la synchronisation avec Azure AD est risquée, car elle risque d’entraîner des problèmes de configuration, ce qui peut entraîner l’endommagement des données dans votre annuaire en ligne.

- À mesure que les produits évoluent, Microsoft continuera à vérifier les configurations de synchronisation standard dans lesquelles toutes les forêts appropriées sont synchronisées. Les clients disposant de configurations de synchronisation personnalisées sont chargés de s’assurer que leurs configurations apportent les attributs et valeurs appropriés dans Azure AD. 

## <a name="related-information"></a>Informations connexes

- [Qu’est-ce que l’identité hybride](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity)

- [Synchronisation Azure AD Connect : comprendre et personnaliser la synchronisation](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis)

- [Topologies pour Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-topologies)

- [Synchronisation Azure AD Connect : attributs synchronisés avec Azure Active Directory](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)
