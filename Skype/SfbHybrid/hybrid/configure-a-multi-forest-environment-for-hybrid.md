---
title: Déployer une topologie de forêt de ressources
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: Les sections suivantes fournissent des instructions sur la configuration d’un environnement possédant plusieurs forêts dans un modèle de forêt de ressources/utilisateur afin de fournir des fonctionnalités Skype entreprise dans un scénario hybride.
ms.openlocfilehash: acfca3b29407b019b87f5429906dbc72b4ef7dc3
ms.sourcegitcommit: 0835f4335ebc8ca53b8348e0b1b906828eb4e13e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/28/2020
ms.locfileid: "43918683"
---
# <a name="deploy-a-resource-forest-topology"></a>Déployer une topologie de forêt de ressources
 
Les sections suivantes fournissent des instructions sur la configuration d’un environnement possédant plusieurs forêts dans un modèle de forêt de ressources/utilisateur afin de fournir des fonctionnalités Skype entreprise dans un scénario hybride. 
  
![Environnement à forêts multiples pour les environnements hybrides](../../sfbserver/media/5f079435-b252-4a6a-9638-3577d55b2873.png)
  
## <a name="topology-requirements"></a>Configuration requise pour la topologie

Plusieurs forêts d’utilisateurs sont prises en charge. Gardez les éléments suivants à l’esprit : 
    
- Pour les versions de Lync Server et Skype entreprise Server prises en charge dans une configuration hybride, voir [Server version Requirements](plan-hybrid-connectivity.md#server-version-requirements) dans [plan Hybrid Connectivity between Skype for Business server and Office 365](plan-hybrid-connectivity.md).
    
- Exchange Server peut être déployé dans une ou plusieurs forêts, qui peuvent inclure ou non la forêt contenant Skype entreprise Server. Assurez-vous que vous avez appliqué la dernière mise à jour cumulative.
    
- Pour plus d’informations sur la coexistence avec Exchange Server, notamment les critères de prise en charge et les limites dans les différentes combinaisons de en local et en ligne, voir [prise en charge des fonctionnalités](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support) dans [plan to integrate Skype for Business and Exchange](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md).
    
  
## <a name="user-homing-considerations"></a>Considérations relatives à l’hébergement des utilisateurs

Les utilisateurs de Skype entreprise hébergés sur site peuvent avoir Exchange hébergé sur site ou en ligne. Les utilisateurs de Skype entreprise Online doivent utiliser Exchange Online pour une expérience optimale ; Toutefois, cela n’est pas obligatoire. Exchange sur site n’est pas nécessaire pour mettre en œuvre Skype entreprise dans les deux cas.
  
## <a name="configure-forest-trusts"></a>Configurer des approbations de forêt

Dans une topologie de forêt de ressources, les forêts de ressources hébergeant Skype entreprise Server doivent approuver chaque forêt de comptes contenant des comptes d’utilisateurs qui y accéderont. Si vous avez plusieurs forêts d’utilisateurs, pour activer l’authentification entre forêts, il est important que le routage des suffixes de noms soit activé pour chacune de ces approbations de forêt. Pour obtenir des instructions, consultez la rubrique [gestion des approbations de forêt](https://technet.microsoft.com/library/cc772440.aspx). Si Exchange Server est déployé dans une autre forêt et qu’il fournit des fonctionnalités pour les utilisateurs de Skype entreprise, la forêt hébergeant Exchange doit approuver la forêt qui héberge Skype entreprise Server. Par exemple, si Exchange a été déployé dans la forêt de comptes, cela signifie qu’une approbation bidirectionnelle entre le compte et les forêts Skype entreprise est requise dans cette configuration.
  
## <a name="synchronize-accounts-into-the-forest-hosting-skype-for-business"></a>Synchroniser les comptes dans la forêt hébergeant Skype entreprise

Lorsque Skype entreprise Server est déployé dans une forêt (une forêt de ressources), mais fournit des fonctionnalités aux utilisateurs dans une ou plusieurs autres forêts (forêts de comptes), les utilisateurs des autres forêts doivent être représentés comme des objets utilisateur désactivés dans la forêt où Skype entreprise Server est déployé. Un produit de gestion des identités, tel que Microsoft Identity Manager, doit être déployé et configuré pour mettre en service et synchroniser les utilisateurs des forêts de comptes dans la forêt où Skype entreprise Server est déployé. Les utilisateurs doivent être synchronisés avec la forêt hébergeant Skype entreprise Server en tant qu’objets utilisateur désactivés. Les utilisateurs ne peuvent pas être synchronisés en tant qu’objets contact Active Directory, car Azure Active Directory Connect ne synchronise pas correctement les contacts dans Azure AD pour une utilisation avec Skype.
  
Quelle que soit la configuration à forêts multiples, la forêt qui héberge Skype entreprise Server peut également fournir des fonctionnalités pour les utilisateurs activés qui existent dans la même forêt.
  
Pour obtenir une synchronisation d’identité correcte, les attributs suivants doivent être synchronisés : 
  
|**Forêts d’utilisateurs**|**Forêts de ressources**|
|:-----|:-----|
|attribut de lien de compte choisi  <br/> |attribut de lien de compte choisi  <br/> |
|mail  <br/> |mail  <br/> |
|ProxyAddresses  <br/> |ProxyAddresses  <br/> |
|ObjectSID  <br/> |msRTCSIP-OriginatorSID  <br/> |
   
L' [attribut de lien de compte choisi](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts) sera utilisé comme ancre source. Si vous avez un autre attribut non modifiable que vous préférez utiliser, vous pouvez le faire ; Assurez-vous simplement de modifier la règle de revendications AD FS et sélectionnez l’attribut pendant la configuration de AAD Connect.
  
Ne synchronisez pas les UPN entre les forêts. Nous avons trouvé pendant les tests que nous avions besoin d’utiliser un UPN unique pour chaque forêt d’utilisateurs, car vous ne pouvez pas utiliser le même nom d’utilisateur principal dans plusieurs forêts. Par conséquent, nous avons présenté deux possibilités pour synchroniser l’UPN ou non pour la synchronisation. 
  
- Si le nom d’utilisateur principal unique de chaque forêt utilisateur n’a pas été synchronisé avec l’objet désactivé associé dans la forêt de ressources, l’authentification unique (SSO) est interrompue au moins lors de la tentative de connexion initiale (en supposant que l’utilisateur a sélectionné l’option Enregistrer le mot de passe). Dans le client Skype entreprise, nous partons du principe que les valeurs SIP/UPN sont identiques. Étant donné que l’adresse SIP dans ce scénario est user@company.com, mais que l’UPN de l’objet activé dans la forêt d’utilisateurs est en fait user@contoso.company.com, la tentative de connexion initiale échoue et l’utilisateur est invité à entrer des informations d’identification. Lors de la saisie de l’UPN correct/réel, la demande d’authentification est exécutée sur les contrôleurs de domaine dans la forêt d’utilisateurs, et la connexion réussit.
    
- Si le nom d’utilisateur unique (UPN) unique de chaque forêt d’utilisateurs a été synchronisé avec l’objet désactivé associé dans la forêt de ressources, l’authentification AD FS échoue. La règle de correspondance trouve l’UPN sur l’objet dans la forêt de ressources, qui a été désactivée et qui n’a pas pu être utilisée pour l’authentification. 
    
## <a name="create-an-office-365-organization"></a>Créer une organisation Office 365

Vous devrez ensuite approvisionner une organisation Office 365 pour l’utiliser avec votre déploiement. Pour plus d’informations, consultez [la rubrique abonnements, licences, comptes et clients pour les offres Cloud de Microsoft](https://docs.microsoft.com/office365/enterprise/subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings). 
  
## <a name="configure-active-directory-federation-services"></a>Configurer les services ADFS (Active Directory Federation Services)

Une fois que vous avez un client, vous devez configurer les services ADFS (Active Directory Federation Services) dans chacune des forêts d’utilisateurs. Cela suppose que vous disposiez d’une adresse SIP et SMTP et d’un nom d’utilisateur principal (UPN) uniques pour chaque forêt. AD FS est facultatif et utilisé ici pour obtenir l’authentification unique (SSO). DirSync avec synchronisation de mot de passe est également pris en charge et peut également être utilisé à la place d’AD FS. 
  
Seuls les déploiements avec SIP/SMTP et UPN correspondants ont été testés. Le fait de ne pas avoir un SIP/SMTP/UPN correspondant peut entraîner des fonctionnalités réduites, telles que des problèmes liés à l’intégration d’Exchange et à l’authentification unique. 
  
À moins que vous n’utilisiez un SIP/SMTP/UPN unique pour les utilisateurs de chaque forêt, vous pouvez toujours rencontrer des problèmes d’authentification unique, quel que soit l’endroit où AD FS est déployé : 
  
- Approbations à sens unique ou bidirectionnelles entre les forêts de ressources/d’utilisateurs et la batterie de serveurs AD FS déployée dans chaque forêt d’utilisateurs, tous les utilisateurs partagent un domaine SIP/SMTP commun, mais un nom UPN unique pour chaque forêt d’utilisateurs. 
    
- Approbations bidirectionnelles entre les forêts de ressources/d’utilisateurs et la batterie de serveurs AD FS déployée uniquement dans la forêt de ressources, tous les utilisateurs partagent un domaine SIP/SMTP commun mais un nom UPN unique pour chaque forêt d’utilisateurs. 
    
En plaçant une batterie AD FS dans chaque forêt d’utilisateurs et en utilisant un SIP/SMTP/UPN unique pour chaque forêt, nous résolvons les deux problèmes. Seuls les comptes de cette forêt utilisateur spécifique seraient recherchés et mis en correspondance lors des tentatives d’authentification. Cela vous permettra de fournir un processus d’authentification plus transparent. 
  
Il s’agit d’un déploiement standard de Windows Server 2012 R2 AD FS qui doit être opérationnel avant de continuer. Pour obtenir des instructions, consultez [la rubrique installation d’AD FS 2012 R2 pour Office 365](https://blogs.technet.com/b/rmilne/archive/2014/04/28/how-to-install-adfs-2012-r2-for-office-365.aspx). 
  
Une fois déployé, vous devez modifier la règle de revendications pour qu’elle corresponde à l’ancre source sélectionnée précédemment. Dans la console MMC AD FS, sous approbations de partie de confiance, cliquez avec le bouton droit sur **plateforme d’identité Microsoft Office 365**, puis cliquez sur **modifier les règles de revendication**. Modifiez la première règle et définissez ObjectSID sur **employeeNumber**. 
  
![Écran des règles de modification à plusieurs forêts](../../sfbserver/media/f5d485bd-52cc-437f-ba71-217f8902056c.png)
  
## <a name="configure-aad-connect"></a>Configurer AAD Connect

Dans les topologies de forêt de ressources, il est nécessaire que les attributs utilisateur de la forêt de ressources et de toutes les forêts de comptes soient synchronisés avec Azure AD. Pour ce faire, la méthode la plus simple et recommandée est d’avoir Azure AD Connect synchroniser et fusionner les identités des utilisateurs de *toutes les* forêts ayant activé les comptes d’utilisateur et la forêt qui contient Skype entreprise. Pour plus d’informations, reportez-vous à la rubrique [configurer Azure ad Connect pour Skype entreprise et teams](configure-azure-ad-connect.md).

Notez que AAD Connect ne fournit pas de synchronisation sur site entre les forêts de comptes et de ressources. Qui doivent être configurés séparément à l’aide de Microsoft Identity Manager ou d’un produit similaire, comme décrit précédemment.
  
Lorsque vous avez terminé et que la connexion AAD est fusionnée, si vous examinez un objet dans le métaverse, vous devriez voir un résultat semblable à celui-ci : 
  
![Écran d’objet métaverse multi-Forest](../../sfbserver/media/16379880-2de3-4c43-b219-1551f5dec5f6.png)
  
Les attributs verts en surbrillance ont été fusionnés à partir d’Office 365, le jaune sont issus de la forêt d’utilisateurs et le bleu est de la forêt de ressources. 
  
Il s’agit d’un utilisateur test, et vous pouvez voir que AAD Connect a identifié le ancre source et le cloudSourceAnchor de l’utilisateur et les objets de la forêt de ressources d’Office 365, dans notre cas 1101, qui est le employeeNumber sélectionné précédemment. Il a ensuite pu fusionner cet objet dans ce que vous voyez ci-dessus. 
  
Pour plus d’informations, consultez [la rubrique intégration de vos répertoires locaux à Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/). 
  
La connexion AAD doit être installée à l’aide des valeurs par défaut, à l’exception des suivantes : 
  
1. Authentification unique : les services AD FS sont déjà déployés et fonctionnent : sélectionnez **ne pas configurer**.
    
2. Connectez vos annuaires : Ajoutez tous les domaines.
    
3. Identifier les utilisateurs dans les répertoires locaux : sélectionnez **User Identities EXISTS dans plusieurs répertoires**, puis sélectionnez les attributs **objectSID** et **msExchangeMasterAccountSID.** .
    
4. Identifier les utilisateurs dans Azure AD : ancre source : sélectionnez l’attribut que vous avez choisi après avoir lu [sélection d’un attribut ancre source approprié](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts#selecting-a-good-sourceanchor-attribute), nom d’utilisateur principal- **userPrincipalName**.
    
5.  Fonctionnalités facultatives : Déterminez si vous avez déployé Exchange hybride.
    
    > [!NOTE]
    >  Si vous avez uniquement Exchange Online, il peut y avoir un problème avec les échecs OAuth lors de la découverte automatique en raison de la redirection CNAMe. Pour corriger cela, vous devez définir l’URL de découverte automatique Exchange en exécutant l’applet de commande suivante à partir de Skype entreprise Server Management Shell :
    >
    > ```powershell
    > Set-CsOAuthConfiguration -ExchangeAutoDiscoverURL https://autodiscover-s.outlook.com/autodiscover/autodiscover.svc 
    > ```
    
6.  Batterie de serveurs AD FS : sélectionnez **utiliser une batterie de serveurs Windows Server 2012 R2 AD FS existante** et entrez le nom du serveur AD FS.
    
7.  Terminez l’Assistant et effectuez les validations nécessaires.
    
## <a name="configure-hybrid-connectivity-for-skype-for-business-server"></a>Configuration de la connectivité hybride pour Skype entreprise Server

Suivez les meilleures pratiques en matière de configuration de Skype entreprise hybride. Pour plus d’informations, reportez-vous à [plan Hybrid Connectivity](plan-hybrid-connectivity.md) et [configure Hybrid Connectivity](configure-hybrid-connectivity.md). 
  
## <a name="configure-hybrid-connectivity-for-exchange-server"></a>Configurer la connectivité hybride pour Exchange Server

Si nécessaire, suivez les meilleures pratiques en matière de configuration d’Exchange hybride. Pour plus d’informations, consultez la rubrique [déploiements hybrides Exchange Server](https://docs.microsoft.com/exchange/exchange-hybrid). 
  
