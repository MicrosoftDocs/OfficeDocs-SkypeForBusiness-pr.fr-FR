---
title: Configurer Azure AD se connecter
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Instructions pour configurer Azure Connect AD dans un environnement hybride.
ms.openlocfilehash: a63f5bde6db1f9d04e2a1fbf03dd4434d1b7c8b3
ms.sourcegitcommit: a3181bc3707b09c1e3f87c343b38259fdc6dabd2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/14/2018
ms.locfileid: "27264924"
---
# <a name="configure-azure-ad-connect-for-teams-and-skype-for-business"></a>Configurer Azure AD Connect pour les équipes et Skype pour les entreprises
 
Les organisations qui ont Skype pour Business Server (ou Lync Server) local et qui sont envisagez d’utiliser des équipes ou Skype pour Business Online doivent configurer Azure AD se connecter pour synchroniser leur répertoire local avec Office 365, comme décrit dans ce document.  Cela inclut les organisations déplacement directement à partir de Skype pour l’entreprise locale aux équipes. En particulier, organisations avec Skype pour Business local doivent vous assurer que les attributs msRTCSIP appropriés sont synchronisées dans Azure AD. 

> [!NOTE]
> Utilisateurs équipes existants qui ont également Skype pour Business local devra leur Skype pour compte local de Business déplacé vers le nuage afin d’obtenir complète des fonctionnalités--telles que la possibilité d’interagir avec Skype pour les utilisateurs professionnels et communiquer avec les utilisateurs dans les organisations fédérées. Même si l’utilisateur utilisera uniquement les équipes, cette Skype en ligne pour un compte professionnel est requis par l’infrastructure pour fournir des fonctionnalités supplémentaires.  Pour cette migration ait lieu, vous devez vous assurer que Azure AD se connecter est configuré de sorte que vous pouvez activer hybride.
 

## <a name="background-information"></a>Informations générales

Azure Active Directory se connecter conserve votre Active Directory local en permanence synchronisé avec Office 365.  Votre annuaire local reste la source d’autorité d’identité et de votre environnement local, les modifications sont synchronisées dans Azure AD. Pour plus d’informations, voir [Azure AD Sync se connecter](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/how-to-connect-sync-whatis).  Même si vous ne déplacez pas tous les utilisateurs sur site vers le nuage, tous les utilisateurs qui utilisent des équipes, Skype pour Business local ou Skype pour Business Online doivent être synchronisés sur site dans Azure AD pour assurer la communication entre les utilisateurs en ligne et en local . *Les utilisateurs de votre organisation seront représentés dans vos annuaires en ligne et sur site.*


## <a name="configuring-azure-ad-when-you-have-skype-for-business-server"></a>Configuration d’Azure AD lorsque vous avez Skype pour Business Server 

Si vous avez une forêt d’Active Directory sur site ou de plusieurs forêts, Azure AD Connect peut être utilisée dans diverses topologies prises en charge, comme décrit dans les [Topologies pour Azure AD se connecter](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/plan-connect-topologies).  Du point de vue de Skype pour Business Server, il existe trois variantes principales : 

1. Une forêt unique, qui contient les identités utilisateur faisant autorité et héberge Skype pour Business Server. 

2. Plusieurs forêts, seul héberge Skype pour Business Server, ainsi qu’un ou plusieurs autres forêts qui contiennent les identités des utilisateurs faisant autorité (les forêts compte). 

3. Plusieurs déploiements de Skype pour Business Server dans plusieurs forêts. Condition certaines conditions sont remplies, les entreprises peuvent consolider leurs ces plusieurs déploiements dans un seul client Office 365.

### <a name="single-forest"></a>Forêt unique 

Si les comptes d’utilisateurs et Skype pour les entreprises sont tous hébergés dans une seule forêt, vous devez vous assurer que Azure AD Connect est configuré pour synchroniser les utilisateurs de cette forêt dans Azure AD.  Bien que l’Assistant d’installation Azure AD Connect propose différentes options de, les attributs appropriés sont automatiquement synchronisées dans Azure Active Directory. Il est conseillé aux utilisateurs par rapport à modifier les règles de synchronisation intégré et/ou les connecteurs qui gèrent la configuration (qui n’est pas possible de l’Assistant d’installation).  

### <a name="multiple-forests-with-one-skype-for-business-deployment"></a>Plusieurs forêts avec un Skype pour le déploiement d’entreprise 

Ce scénario est souvent appelé une topologie de forêt de ressources. Les identités des utilisateurs faisant autoritées sont hébergées dans une ou plusieurs forêts compte et Skype pour les entreprises est déployé dans une forêt de ressources distincts (qui peut également héberger les identités utilisateur faisant autorité). En règle générale, Skype pour les identités faisant autorité des utilisateurs de l’entreprise peut être dans la même forêt que Skype pour Business Server et/ou dans une autre forêt, fournies : 

- Les utilisateurs dont les identités faisant autoritées à partir du compte de forêts sont représentés dans la forêt de ressources (où Skype pour Business Server est déployé) en tant qu’objets utilisateur désactivés et l’attribut msRTCSIP-OriginatorSID dans la forêt de ressources correspond à l’identificateur de sécurité dans le forêt de compte. Pour plus d’informations, consultez [configurer un environnement à forêts multiples pour un environnement hybride Skype pour les entreprises](configure-a-multi-forest-environment-for-hybrid.md).

- La forêt de ressources héberge Skype pour Business Server approuve les forêts compte.  

- Tous les objets utilisateur pertinents et les attributs d’identité à la fois (à partir de forêts de comptes) et Skype pour les entreprises (à partir de forêt de ressources) sont synchronisées dans Azure Active Directory avec les valeurs appropriées via Azure AD se connecter.  

 Pour obtenir l’objet approprié et synchronisation des attributs dans Azure Active Directory dans un [déploiement dans plusieurs forêts locales scénario](configure-a-multi-forest-environment-for-hybrid.md), Microsoft recommande vivement à l’aide d’Azure AD connexion de synchronisation à partir de toutes les forêts que vous ont activé les comptes d’utilisateurs et de la forêt qui contient Skype pour les entreprises.  En supposant que la synchronisation de toutes les forêts, vous devez alors configurer Azure AD se connecter pour fusionner ces identités et synchroniser avec Azure AD. Azure AD Connect est conçu pour gérer ce scénario et propose l’option intégrée dans l’Assistant d’installation sur cette configuration, y compris la configuration ancres pour participer à des identités.  Choisir les éléments suivants : les identités utilisateur existent sur plusieurs annuaires. Correspondance à l’aide--> attributs ObjectSID et msExchangeMasterAccountSID.


### <a name="multiple-skype-for-business-server-deployments-in-multiple-forests"></a>Plusieurs Skype pour les déploiements de serveur d’entreprise dans plusieurs forêts 

Dans ce scénario, il existe plusieurs forêts, chaque conteneur Skype pour Business Server et un seul client Office 365.  Chaque forêt contenant Skype pour Business Server peut être synchronisé dans Azure AD pour ce client à l’aide de DAS se connecter. Au plus qu’une seule forêt peut être configurée pour Skype pour un environnement hybride Business à un moment donné. Avant d’activer la configuration hybride dans une forêt, tous les domaines SIP de toutes les autres forêts doivent être désactivées à l’aide de [disable-csonlineSipDomain](https://docs.microsoft.com/en-us/powershell/module/skype/disable-csonlinesipdomain). Pour plus d’informations sur la façon de consolider un tel environnement dans Office 365, voir [consolidation Cloud pour les équipes et Skype pour les entreprises](cloud-consolidation.md).

## <a name="general-requirements"></a>Exigences générales 

Les équipes et Skype pour des services professionnels en ligne nécessitent que les attributs Active Directory appropriés existent et sont remplis dans Azure AD.  Recommandation générale de Microsoft consiste à synchroniser toutes les forêts qui contiennent des identités d’utilisateur, ainsi que les forêts qui contiennent des Skype pour Business Server.

 Si les identités des utilisateurs existent dans plusieurs forêts, Azure AD se connecter doit effectuer la fusion. Lorsque ce guide est suivi, Azure AD Connect synchronise automatiquement les attributs appropriés, condition que vous ne modifiez pas les connecteurs ou les règles de synchronisation dans Azure AD se connecter. 
  
Si vous ne sont pas synchronisez à partir de toutes les forêts qui contiennent des identités d’utilisateur et le Skype pour le déploiement de serveur d’entreprise, vous devez toujours vérifier l’identité appropriée et Skype pour les attributs de l’entreprise sont correctes dans Azure AD pour n’importe quel utilisateur à l’aide des équipes ou Skype pour les entreprises (si locale ou en ligne)--qui nécessitera probablement supplémentaires local la synchronisation d’annuaires. Pour plus d’informations, voir [synchronisation Azure AD Connect : attributs synchronisés avec Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized).

Dans ces scénarios, il est de la responsabilité du client pour garantir une configuration correcte de renseigner les attributs dans Azure AD. Tenez compte des points suivants : 

- À l’aide d’une configuration non standard pour la synchronisation avec Azure AD est risquée car elle peut entraîner une mauvaise configuration, ce qui peut provoquer une altération des données dans votre répertoire en ligne.

- Produits évoluent, Microsoft continueront à vérifier les configurations standard de synchronisation dans laquelle toutes les forêts pertinents sont synchronisés. Les clients avec des configurations de synchronisation personnalisé sont responsables de que leurs configurations offrent les attributs appropriés et les valeurs dans Azure AD. 

## <a name="related-information"></a>Informations connexes

- [Nouveautés d’identité hybride](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/whatis-hybrid-identity?toc=%2Fen-us%2Fazure%2Factive-directory%2Fhybrid%2FTOC.json&bc=%2Fen-us%2Fazure%2Fbread%2Ftoc.json)

- [Azure AD Connect sync : comprendre et personnaliser la synchronisation](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/how-to-connect-sync-whatis)

- [Connecter des topologies pour Azure AD](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/plan-connect-topologies)

- [Azure AD Connect sync : attributs synchronisés avec Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)
