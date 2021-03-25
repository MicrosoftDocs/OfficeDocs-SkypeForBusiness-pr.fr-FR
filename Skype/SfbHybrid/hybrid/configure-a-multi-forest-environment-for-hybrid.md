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
description: Les sections suivantes fournissent des instructions sur la configuration d’un environnement qui possède plusieurs forêts dans un modèle de forêt ressource/utilisateur afin de fournir des fonctionnalités Skype Entreprise dans un scénario hybride.
ms.openlocfilehash: 2f4d0c84997dcc0d19439210e72eaf01a7a1ff26
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119003"
---
# <a name="deploy-a-resource-forest-topology"></a>Déployer une topologie de forêt de ressources
 
Les sections suivantes fournissent des instructions sur la configuration d’un environnement qui possède plusieurs forêts dans un modèle de forêt ressource/utilisateur afin de fournir des fonctionnalités Skype Entreprise dans un scénario hybride. 
  
![Environnement à forêts multiples pour les environnements hybrides](../../sfbserver/media/5f079435-b252-4a6a-9638-3577d55b2873.png)
  
## <a name="topology-requirements"></a>Configuration requise pour la topologie

Plusieurs forêts d’utilisateurs sont pris en charge. Gardez les éléments suivants à l’esprit : 
    
- Pour les versions de Lync Server et Skype Entreprise Server pris en charge dans une configuration hybride, voir La configuration requise pour la [version](plan-hybrid-connectivity.md#server-version-requirements) du serveur dans Planifier la connectivité hybride entre Skype Entreprise Server et [Microsoft 365 ou Office 365.](plan-hybrid-connectivity.md)
    
- Exchange Server peuvent être déployés dans une ou plusieurs forêts, qui peuvent inclure ou non la forêt contenant Skype Entreprise Server. Assurez-vous que vous avez appliqué la dernière mise à jour cumulative.
    
- Pour plus d’informations sur la coexistence avec Exchange Server, notamment sur les critères de prise [](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support) en charge et les limitations dans différentes combinaisons de sites locaux et en ligne, voir La prise en charge des fonctionnalités dans Plan d’intégration de Skype Entreprise et [Exchange.](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)
    
  
## <a name="user-homing-considerations"></a>Considérations sur l’homeing des utilisateurs

Les utilisateurs de Skype Entreprise sur site peuvent avoir Exchange sur site ou en ligne. Les utilisateurs de Skype Entreprise Online doivent utiliser Exchange Online pour une expérience optimale. toutefois, cela n’est pas obligatoire. Exchange local n’est pas requis pour implémenter Skype Entreprise dans les deux cas.
  
## <a name="configure-forest-trusts"></a>Configurer les trusts de forêt

Dans une topologie de forêt de ressources, les forêts de ressources hébergeant Skype Entreprise Server doivent faire confiance à chaque forêt de comptes qui contient les comptes des utilisateurs qui y accèderont. Si vous avez plusieurs forêts d’utilisateurs, pour activer l’authentification entre forêts, il est important que le routage de suffixe de nom soit activé pour chacune de ces bases de données de forêt. Pour plus d’instructions, voir [Managing Forest Trusts](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772440(v=ws.11)). Si vous avez déployé Exchange Server dans une autre forêt et qu’il fournit des fonctionnalités aux utilisateurs de Skype Entreprise, la forêt qui héberge Exchange doit faire confiance à la forêt hébergeant Skype Entreprise Server. Par exemple, si Exchange a été déployé dans la forêt de comptes, cela signifierait effectivement qu’une relation d’confiance double entre le compte et les forêts Skype Entreprise est requise dans cette configuration.
  
## <a name="synchronize-accounts-into-the-forest-hosting-skype-for-business"></a>Synchroniser des comptes dans la forêt hébergeant Skype Entreprise

Lorsque Skype Entreprise Server est déployé dans une forêt (forêt de ressources), mais fournit des fonctionnalités aux utilisateurs dans une ou plusieurs autres forêts (forêts de comptes), les utilisateurs des autres forêts doivent être représentés en tant qu’objets utilisateur désactivés dans la forêt où Skype Entreprise Server est déployé. Un produit de gestion des identités, tel que Microsoft Identity Manager, doit être déployé et configuré pour mettre en service et synchroniser les utilisateurs des forêts de comptes dans la forêt où Skype Entreprise Server est déployé. Les utilisateurs doivent être synchronisés dans la forêt hébergeant Skype Entreprise Server en tant qu’objets utilisateur désactivés. Les utilisateurs ne peuvent pas être synchronisés en tant qu’objets contact Active Directory, car Azure Active Directory Connect ne synchronise pas correctement les contacts dans Azure AD pour une utilisation avec Skype.
  
Quelle que soit la configuration à forêts multiples, la forêt qui héberge Skype Entreprise Server peut également fournir des fonctionnalités à tous les utilisateurs activés qui existent dans la même forêt.
  
Pour obtenir une synchronisation d’identité appropriée, les attributs suivants doivent être synchronisés : 
  
|**Forêts d’utilisateurs**|**Forêts de ressources**|
|:-----|:-----|
|attribut de lien de compte choisi  <br/> |attribut de lien de compte choisi  <br/> |
|messagerie  <br/> |messagerie  <br/> |
|ProxyAddresses  <br/> |ProxyAddresses  <br/> |
|ObjectSID  <br/> |msRTCSIP-OriginatorSID  <br/> |
   
[L’attribut de lien de compte](/azure/active-directory/hybrid/plan-connect-design-concepts) choisi sera utilisé comme ancre source. Si vous avez un attribut différent et immuable que vous préférez utiliser, vous pouvez le faire . il vous suffit de modifier la règle de revendications AD FS et de sélectionner l’attribut pendant la configuration AAD Connect.
  
Ne synchronisez pas les UPN entre les forêts. Lors des tests, nous avons constaté que nous devaient utiliser un UPN unique pour chaque forêt d’utilisateurs, car vous ne pouvez pas utiliser le même UPN dans plusieurs forêts. Par conséquent, deux possibilités s’offrent à nous : synchroniser l’UPN ou ne pas se synchroniser. 
  
- Si l’UPN unique de chaque forêt d’utilisateurs n’a pas été synchronisé avec l’objet désactivé associé dans la forêt de ressources, l' sign-on unique (SSO) est rompue pour au moins la première tentative de déconnexions (en supposant que l’utilisateur a sélectionné l’option d’enregistrer le mot de passe). Dans le client Skype Entreprise, nous partons du principe que les valeurs SIP/UPN sont identiques. Étant donné que l’adresse SIP dans ce scénario est user@company.com, mais que l’UPN de l’objet activé dans la forêt d’utilisateurs est en fait user@contoso.company.com, la tentative de connexion initiale échouerait et l’utilisateur serait invité à entrer des informations d’identification. Lors de la saisie de leur UPN correct/réel, la demande d’authentification est effectuée sur les contrôleurs de domaine dans la forêt d’utilisateurs et la signature réussit.
    
- Si l’UPN unique de chaque forêt d’utilisateurs a été synchronisé avec l’objet désactivé associé dans la forêt de ressources, l’authentification AD FS échouerait. La règle correspondante trouve l’UPN sur l’objet dans la forêt de ressources, qui a été désactivé et n’a pas pu être utilisé pour l’authentification. 
    
## <a name="create-a-microsoft-365-or-office-365-organization"></a>Créer une organisation Microsoft 365 ou Office 365

Vous devrez ensuite mettre en service une organisation Microsoft 365 ou Office 365 à utiliser avec votre déploiement. Pour plus d’informations, voir [Abonnements, licences,](/office365/enterprise/subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings)comptes et clients pour les offres cloud de Microsoft. 
  
## <a name="configure-active-directory-federation-services"></a>Configurer les services de fédération Active Directory

Une fois que vous avez un client, vous devez configurer les services AD FS (Active Directory Federation Services) dans chacune des forêts d’utilisateurs. Cela suppose que vous avez une adresse SIP et SMTP unique et un nom d’utilisateur principal (UPN) pour chaque forêt. AD FS est facultatif et est utilisé ici pour obtenir l' sign-on unique (SSO). La synchronisation DirSync avec mot de passe est également prise en charge et peut également être utilisée à la place d’AD FS. 
  
Seuls les déploiements avec SIP/SMTP et UPN correspondants ont été testés. Le fait de ne pas disposer de correspondances SIP/SMTP/UPN peut entraîner une réduction des fonctionnalités, telles que des problèmes liés à l’intégration d’Exchange et à l' cesso. 
  
À moins d’utiliser un SIP/SMTP/UPN unique pour les utilisateurs de chaque forêt, vous pouvez toujours être en butte à des problèmes DSO, quel que soit l’endroit où AD FS est déployé : 
  
- Les confiances à sens unique ou double entre les forêts de ressources/utilisateurs avec une batterie de serveurs AD FS déployée dans chaque forêt d’utilisateurs, tous les utilisateurs partagent un domaine SIP/SMTP commun, mais un UPN unique pour chaque forêt d’utilisateurs. 
    
- Les relations d’confiance entre les forêts ressource/utilisateur avec une batterie AD FS déployée uniquement dans la forêt de ressources, tous les utilisateurs partagent un domaine SIP/SMTP commun, mais un UPN unique pour chaque forêt d’utilisateurs. 
    
En plaçant une batterie de serveurs AD FS dans chaque forêt d’utilisateurs et en utilisant un SIP/SMTP/UPN unique pour chaque forêt, nous résoudons les deux problèmes. Seuls les comptes de cette forêt d’utilisateurs spécifiques sont recherchés et correspondent lors des tentatives d’authentification. Cela vous permettra de fournir un processus d’authentification plus transparent. 
  
Il s’agit d’un déploiement standard de Windows Server 2012 R2 AD FS et doit fonctionner avant de continuer. Pour obtenir des instructions, voir Comment installer [AD FS 2012 R2 pour Microsoft 365 ou Office 365](https://blogs.technet.com/b/rmilne/archive/2014/04/28/how-to-install-adfs-2012-r2-for-office-365.aspx). 
  
Une fois le déploiement déployé, vous devez modifier la règle de revendications pour qu’elle corresponde à l’ancre source sélectionnée précédemment. Dans la MMC AD FS, sous Trusts de partie de confiance, cliquez avec le bouton droit sur Plateforme d’identités **Microsoft 365** ou plateforme d’identité **Microsoft Office 365,** puis sélectionnez Modifier les règles de **revendication.** Modifiez la première règle et modifiez ObjectSID en **employeeNumber**. 
  
![Écran Modifier les règles à forêts multiples](../../sfbserver/media/f5d485bd-52cc-437f-ba71-217f8902056c.png)
  
## <a name="configure-aad-connect"></a>Configurer AAD Connect

Dans les topologies de forêt de ressources, il est nécessaire que les attributs utilisateur de la forêt de ressources et de toutes les forêts de comptes soient synchronisés dans Azure AD. La méthode la plus simple et recommandée consiste à faire en sorte  qu’Azure AD Connect synchronise et fusionne les identités des utilisateurs de toutes les forêts qui ont activé les comptes d’utilisateur et la forêt qui contient Skype Entreprise. Pour plus d’informations, [voir Configurer Azure AD Connect pour Skype Entreprise et Teams.](configure-azure-ad-connect.md)

Notez qu’AAD Connect ne fournit pas de synchronisation sur site entre le compte et les forêts de ressources. Celui-ci doit être configuré séparément à l’aide de Microsoft Identity Manager ou d’un produit similaire, comme décrit précédemment.
  
Lorsque vous avez terminé et qu’AAD Connect est en cours de fusion, si vous regardez un objet dans le métaverse, vous devriez voir quelque chose de semblable à ceci : 
  
![Écran d’objet Métaverse à forêts multiples](../../sfbserver/media/16379880-2de3-4c43-b219-1551f5dec5f6.png)
  
Les attributs en surbrillants verts ont été fusionnés à partir de Microsoft 365 ou Office 365, le jaune est issu de la forêt d’utilisateurs et le bleu est issu de la forêt ressource. 
  
Il s’agit d’un utilisateur test et vous pouvez voir qu’AAD Connect a identifié la sourceAnchor et le cloudSourceAnchor de l’utilisateur et les objets de forêt de ressources de Microsoft 365 ou Office 365, dans notre cas 1101, qui est l’employeeNumber sélectionné précédemment. Il a ensuite pu fusionner cet objet dans ce que vous voyez ci-dessus. 
  
Pour plus d’informations, voir Intégrer vos annuaires locaux [à Azure Active Directory.](/azure/active-directory/hybrid/whatis-hybrid-identity) 
  
AAD Connect doit être installé à l’aide des valeurs par défaut, à l’exception des suivantes : 
  
1. Sign-in unique - with AD FS already deployed and working: Select **Do not configure**.
    
2. Connectez vos répertoires : ajoutez tous les domaines.
    
3. Identifiez les utilisateurs dans les répertoires locaux : sélectionnez les identités des **utilisateurs** dans plusieurs répertoires, puis sélectionnez les attributs **ObjectSID** et **msExchangeMasterAccountSID.**
    
4. Identifiez les utilisateurs dans Azure AD : Ancre source : sélectionnez l’attribut que vous avez choisi après avoir lu Sélectionner un attribut [sourceAnchor](/azure/active-directory/hybrid/plan-connect-design-concepts#selecting-a-good-sourceanchor-attribute), Nom d’utilisateur principal - **userPrincipalName**.
    
5.  Fonctionnalités facultatives : sélectionnez si exchange hybride est déployé.
    
    > [!NOTE]
    >  Si vous avez uniquement Exchange Online, il peut y avoir un problème avec les échecs OAuth lors de la découverte automatique en raison de la redirection CNAME. Pour corriger cela, vous devez définir l’URL de découverte automatique Exchange en exécutant la cmdlet suivante à partir de Skype Entreprise Server Management Shell :
    >
    > ```powershell
    > Set-CsOAuthConfiguration -ExchangeAutoDiscoverURL https://autodiscover-s.outlook.com/autodiscover/autodiscover.svc 
    > ```
    
6.  Batterie de serveurs AD FS : sélectionnez Utiliser une batterie **AD FS Windows Server 2012 R2 existante** et entrez le nom du serveur AD FS.
    
7.  Terminez l’Assistant et effectuez les validations nécessaires.
    
## <a name="configure-hybrid-connectivity-for-skype-for-business-server"></a>Configurer la connectivité hybride pour Skype Entreprise Server

Suivez les meilleures pratiques pour configurer Skype Entreprise hybride. Pour plus d’informations, voir [Planifier la connectivité hybride](plan-hybrid-connectivity.md) et configurer la connectivité [hybride.](configure-hybrid-connectivity.md) 
  
## <a name="configure-hybrid-connectivity-for-exchange-server"></a>Configurer la connectivité hybride pour Exchange Server

Si nécessaire, suivez les meilleures pratiques pour configurer Exchange hybride. Pour plus d’informations, [voir Exchange Server déploiements hybrides.](/exchange/exchange-hybrid) 
