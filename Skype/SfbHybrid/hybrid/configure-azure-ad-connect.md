---
title: Configurer Azure AD Connect
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
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
ms.openlocfilehash: 9df0e42224d3186c3d7b5b1748412e9ec9121897
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36160513"
---
# <a name="configure-azure-ad-connect-for-teams-and-skype-for-business"></a>Configurer Azure AD Connect pour teams et Skype entreprise
 
Les organisations qui ont une version locale de Skype entreprise Server (ou Lync Server) et qui envisagent d’utiliser teams ou Skype entreprise Online doivent configurer Azure AD Connect pour synchroniser leur répertoire local avec Office 365, comme décrit dans cet sous.  Cela inclut les organisations qui se déplacent directement de Skype entreprise en local vers Teams. En particulier, les organisations avec Skype entreprise en local doivent s’assurer que les attributs msRTCSIP corrects sont synchronisés avec Azure AD. 

> [!NOTE]
> Les utilisateurs de teams existants qui ont également Skype entreprise en local doivent disposer de leur compte local Skype entreprise déplacés vers le Cloud afin de disposer de toutes les fonctionnalités, telles que la possibilité d’interagir avec les utilisateurs de Skype entreprise et de communiquer avec des utilisateurs dans des organisations fédérées. Même si l’utilisateur ne peut utiliser que Teams, ce compte Skype entreprise en ligne est requis par l’infrastructure pour offrir des fonctionnalités supplémentaires.  Pour que cette migration ait lieu, vous devez vous assurer qu’Azure AD Connect est correctement configuré afin que vous puissiez activer l’environnement hybride.
 

## <a name="background-information"></a>Informations générales

Azure Active Directory Connect maintient la synchronisation permanente de votre Active Directory local avec Office 365.  Votre répertoire local reste la source d’identité faisant autorité et les modifications de votre environnement local sont synchronisées avec Azure AD. Pour plus d’informations, reportez-vous à la rubrique [Azure ad Connect Sync](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/how-to-connect-sync-whatis).  Même si vous ne déplacez pas tous les utilisateurs de l’environnement local vers le Cloud, tous les utilisateurs qui utilisent Teams, Skype entreprise en local ou Skype entreprise Online doivent être synchronisés de l’environnement local vers Azure AD pour garantir la communication entre les utilisateurs locaux et en ligne. . *Les utilisateurs de votre organisation seront représentés dans vos annuaires locaux et en ligne.*


## <a name="configuring-azure-ad-when-you-have-skype-for-business-server"></a>Configuration d’Azure AD lorsque vous avez Skype entreprise Server 

Qu’il s’agisse d’une forêt Active Directory locale ou de plusieurs forêts, Azure AD Connect peut être utilisé dans diverses topologies prises en charge, comme décrit dans [topologies pour Azure ad Connect](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/plan-connect-topologies).  Du point de vue de Skype entreprise Server, il existe trois variantes principales: 

1. Une seule forêt, qui contient les identités des utilisateurs faisant autorité et héberge Skype entreprise Server. 

2. Plusieurs forêts, une seule d’entre elles héberge Skype entreprise Server, ainsi qu’une ou plusieurs autres forêts qui contiennent des identités d’utilisateur faisant autorité (les forêts de comptes). 

3. Plusieurs déploiements de Skype entreprise Server dans plusieurs forêts. Sous réserve que certaines exigences soient satisfaites, les organisations peuvent consolider ces déploiements multiples en un seul client Office 365.

### <a name="single-forest"></a>Forêt unique 

Si les comptes d’utilisateur et Skype entreprise sont tous hébergés dans une forêt unique, vous devez vous assurer qu’Azure AD Connect est configuré pour synchroniser les utilisateurs de cette forêt dans Azure AD.  Bien que l’Assistant Installation d’Azure AD Connect comporte plusieurs options, les attributs appropriés seront automatiquement synchronisés avec Azure Active Directory. Les clients sont avertis de la modification des règles de synchronisation intégrées et/ou des connecteurs qui gèrent la configuration (ce qui n’est pas possible à partir de l’Assistant Installation).  

### <a name="multiple-forests-with-one-skype-for-business-deployment"></a>Plusieurs forêts avec un déploiement de Skype entreprise 

Ce scénario est souvent appelé topologie de forêt de ressources. Les identités de référence des utilisateurs sont hébergées dans une ou plusieurs forêts de comptes, et Skype entreprise est déployé dans une forêt de ressources distincte (qui peut également héberger des identités d’utilisateur faisant autorité). En règle générale, les identités faisant autorité dans les utilisateurs de Skype entreprise peuvent se trouver dans la même forêt que Skype entreprise Server et/ou dans une autre forêt, sous réserve des éléments suivants: 

- Les utilisateurs disposant d’identités de référence provenant de la (des) forêt (s) de comptes sont représentés dans la forêt de ressources (où Skype entreprise Server est déployé) en tant qu’objets utilisateur désactivés, et l’attribut msRTCSIP-OriginatorSID dans la forêt de ressources correspond au SID dans le forêt de comptes. Pour plus d’informations, consultez [la rubrique Configure a multi-Forest Environment for Hybrid Skype for Business](configure-a-multi-forest-environment-for-hybrid.md).

- La forêt de ressources qui héberge Skype entreprise Server approuve les forêts de comptes.  

- Tous les attributs et objets utilisateur pertinents pour l’identité (à partir des forêts de comptes) et Skype entreprise (à partir de la forêt de ressources) sont synchronisés dans Azure AD avec les valeurs correctes via Azure AD Connect.  

 Pour assurer une synchronisation des attributs et des objets corrects dans Azure AD dans un [scénario local sur plusieurs forêts](configure-a-multi-forest-environment-for-hybrid.md), Microsoft recommande vivement d’utiliser Azure ad Connect pour synchroniser toutes les forêts ayant activé les comptes d’utilisateur et la forêt contient Skype entreprise.  En supposant que vous procédiez à une synchronisation à partir de toutes les forêts, vous devez configurer Azure AD Connect pour fusionner ces identités et effectuer une synchronisation avec Azure AD. Azure AD Connect est conçu pour gérer ce scénario, et fournit une option intégrée dans l’Assistant Installation pour le configurer, y compris la configuration des ancres pour joindre des identités.  Choisissez l’une des options suivantes: les identités d’utilisateur existent dans plusieurs répertoires. Associez using--> ObjectSID et les attributs msExchangeMasterAccountSID..


### <a name="multiple-skype-for-business-server-deployments-in-multiple-forests"></a>Plusieurs déploiements de Skype entreprise Server dans plusieurs forêts 

Dans ce scénario, il existe plusieurs forêts, chacune contenant Skype entreprise Server et un seul client Office 365.  Chaque forêt contenant Skype entreprise Server peut être synchronisée dans Azure AD pour ce client à l’aide d’AAD Connect. Au plus, une seule forêt peut être configurée pour Skype entreprise hybride à un moment donné. Avant d’activer l’environnement hybride dans une forêt, tous les domaines SIP de toutes les autres forêts doivent être désactivés à l’aide de [Disable-csonlineSipDomain](https://docs.microsoft.com/en-us/powershell/module/skype/disable-csonlinesipdomain). Pour plus d’informations sur la consolidation d’un environnement de ce type dans Office 365, voir [Cloud consolidation for teams and Skype for Business](cloud-consolidation.md).

## <a name="general-requirements"></a>Conditions générales 

Les services teams et Skype entreprise Online requièrent que les attributs Active Directory corrects existent et soient renseignés dans Azure AD.  La recommandation générale de Microsoft consiste à synchroniser toutes les forêts qui contiennent des identités d’utilisateur, ainsi que toutes les forêts qui contiennent Skype entreprise Server.

 S’il existe des identités d’utilisateurs dans plusieurs forêts, Azure AD Connect doit effectuer la fusion. Lorsque vous suivez ces instructions, Azure AD Connect synchronise automatiquement les attributs corrects, à condition que vous ne modifiez pas les connecteurs ou les règles de synchronisation dans Azure AD Connect. 
  
Si vous ne procédez pas à une synchronisation à partir de toutes les forêts contenant des identités d’utilisateur et le déploiement de Skype entreprise Server, vous devez toujours vous assurer que les attributs Identity et Skype for Business appropriés sont correctement renseignés dans Azure AD pour tout utilisateur qui utilise teams ou Skype pour les entreprises (en local ou en ligne), ce qui nécessitera probablement une synchronisation d’annuaires locale supplémentaire. Pour plus d’informations, reportez-vous à la rubrique [Azure ad Connect Sync: attributs synchronisés avec Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized).

Dans ces scénarios, il incombe au client de s’assurer de la bonne configuration pour remplir les attributs dans Azure AD. Gardez les éléments suivants à l’esprit : 

- L’utilisation d’une configuration non standard pour la synchronisation avec Azure AD est risquée, car cela peut entraîner une erreur de configuration, ce qui pourrait entraîner une altération des données dans votre annuaire en ligne.

- À mesure que les produits évoluent, Microsoft continue de vérifier les configurations de synchronisation standard dans lesquelles toutes les forêts pertinentes sont synchronisées. Les clients ayant des configurations de synchronisation personnalisées sont chargés de s’assurer que leurs configurations offrent les attributs et les valeurs correctes dans Azure AD. 

## <a name="related-information"></a>Informations connexes

- [Qu’est-ce que l’identité hybride](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/whatis-hybrid-identity?toc=%2Fen-us%2Fazure%2Factive-directory%2Fhybrid%2FTOC.json&bc=%2Fen-us%2Fazure%2Fbread%2Ftoc.json)

- [Synchronisation Azure AD Connect: comprendre et personnaliser la synchronisation](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/how-to-connect-sync-whatis)

- [Topologies pour Azure AD Connect](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/plan-connect-topologies)

- [Synchronisation Azure AD Connect: attributs synchronisés avec Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)
