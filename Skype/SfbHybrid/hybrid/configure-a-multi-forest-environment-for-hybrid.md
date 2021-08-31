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
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: Les sections suivantes dcriront comment configurer un environnement qui possède plusieurs forêts dans un modèle de forêt ressource/utilisateur afin de fournir des fonctionnalités dans un scénario hybride.
ms.openlocfilehash: 5a6ca7c559a2c79979a44d8ca7c8555abf432b4d
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58727053"
---
# <a name="deploy-a-resource-forest-topology"></a>Déployer une topologie de forêt de ressources

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

 
Les sections suivantes décrivent comment configurer un environnement qui possède plusieurs forêts dans un modèle de forêt ressource/utilisateur afin de fournir des fonctionnalités dans un scénario hybride. 
  
![Environnement à forêts multiples pour un environnement hybride.](../../sfbserver/media/5f079435-b252-4a6a-9638-3577d55b2873.png)
  
## <a name="topology-requirements"></a>Configuration requise pour la topologie

Plusieurs forêts d’utilisateurs sont pris en charge. Gardez les éléments suivants à l’esprit : 
    
- Pour les versions de Lync Server et Skype Entreprise Server dans une configuration hybride, voir [Planifier la connectivité hybride.](plan-hybrid-connectivity.md)
    
- Exchange Server peuvent être déployés dans une ou plusieurs forêts, qui peuvent inclure ou non la forêt contenant des Skype Entreprise Server. Assurez-vous que vous avez appliqué la dernière mise à jour cumulative.
    
- Pour plus d’informations sur la coexistence avec Exchange Server, notamment sur les critères de prise [](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support) en charge et les limitations dans différentes combinaisons de sites locaux et en ligne, voir Prise en charge des fonctionnalités dans Planifier l’intégration de [Skype Entreprise et Exchange](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md).
    
  
## <a name="user-homing-considerations"></a>Considérations sur l’homeing des utilisateurs

Skype Entreprise les utilisateurs d’une base de données Exchange peuvent être Exchange sur site ou en ligne. Teams utilisateurs doivent utiliser Exchange Online pour une expérience optimale ; toutefois, cela n’est pas obligatoire. Exchange local n’est pas nécessaire pour implémenter Skype Entreprise dans les deux cas.
  
## <a name="configure-forest-trusts"></a>Configurer les trusts de forêt

Dans une topologie de forêt de ressources, les forêts de ressources qui hébergent Skype Entreprise Server doivent faire confiance à chaque forêt de comptes qui contient les comptes des utilisateurs qui y accèderont. 

Si vous avez plusieurs forêts d’utilisateurs, pour activer l’authentification entre forêts, il est important que le routage de suffixe de nom soit activé pour chacune de ces bases de données de forêt. Pour plus d’instructions, voir [Managing Forest Trusts](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772440(v=ws.11)). 

Si vous avez déployé Exchange Server dans une autre forêt et que Exchange fournit des fonctionnalités pour les utilisateurs Skype Entreprise, le Exchange d’hébergement de forêt doit faire confiance à la forêt hébergeant Skype Entreprise Server. Par exemple, si Exchange ont été déployés dans la forêt de comptes, une relation d’Skype Entreprise entre le compte et les forêts de comptes est requise.
  
## <a name="synchronize-accounts-into-the-forest-hosting-skype-for-business"></a>Synchroniser les comptes dans la forêt hébergeant des Skype Entreprise

Supposons Skype Entreprise Server est déployé dans une forêt (une forêt de ressources), mais fournit des fonctionnalités aux utilisateurs dans une ou plusieurs autres forêts (forêts de comptes). Dans ce cas, les utilisateurs des autres forêts doivent être représentés en tant qu’objets utilisateur désactivés dans la forêt où Skype Entreprise Server est déployé.

Vous devez utiliser un produit de gestion des identités, tel que Microsoft Identity Manager, pour mettre en service et synchroniser les utilisateurs des forêts de comptes dans la forêt où Skype Entreprise Server est déployé. Les utilisateurs doivent être synchronisés dans la forêt hébergeant Skype Entreprise Server en tant qu’objets utilisateur désactivés. Les utilisateurs ne peuvent pas être synchronisés en tant qu’objets contact Active Directory, car Azure Active Directory Connecter ne synchronise pas correctement les contacts dans Azure AD pour une utilisation avec Skype.
  
Quelle que soit la configuration à forêts multiples, la forêt qui héberge Skype Entreprise Server peut également fournir des fonctionnalités à tous les utilisateurs activés qui existent dans la même forêt.
  
Pour obtenir une synchronisation d’identité appropriée, les attributs suivants doivent être synchronisés : 
  
|**Forêts d’utilisateurs**|**Forêts de ressources**|
|:-----|:-----|
|attribut de lien de compte choisi  <br/> |attribut de lien de compte choisi  <br/> |
|messagerie  <br/> |messagerie  <br/> |
|ProxyAddresses  <br/> |ProxyAddresses  <br/> |
|ObjectSID  <br/> |msRTCSIP-OriginatorSID  <br/> |
   
[L’attribut de lien de compte](/azure/active-directory/hybrid/plan-connect-design-concepts) choisi sera utilisé comme ancre source. Si vous avez un attribut différent et immuable que vous préférez utiliser, vous pouvez le faire . il vous suffit de modifier la règle de revendications AD FS et de sélectionner l’attribut pendant la configuration Connecter AAD.
  
Ne synchronisez pas les UPN entre les forêts. Vous devez utiliser un UPN unique pour chaque forêt d’utilisateurs, car vous ne pouvez pas utiliser le même UPN dans plusieurs forêts. Par conséquent, il existe deux possibilités : synchroniser l’UPN ou ne pas synchroniser. 
  
- Si l’UPN unique de chaque forêt d’utilisateurs n’a pas été synchronisé avec l’objet désactivé associé dans la forêt de ressources, l' sign-on unique (SSO) est rompue pour au moins la première tentative de déconnexions (en supposant que l’utilisateur a sélectionné l’option d’enregistrer le mot de passe). Dans le Skype Entreprise client, nous partons du principe que les valeurs SIP/UPN sont identiques. Étant donné que l’adresse SIP dans ce scénario est user@company.com, mais que l’UPN de l’objet activé dans la forêt d’utilisateurs est en fait user@contoso.company.com, la tentative de connexion initiale échouerait et l’utilisateur serait invité à entrer des informations d’identification. Lors de la saisie de leur UPN correct, la demande d’authentification est effectuée sur les contrôleurs de domaine dans la forêt d’utilisateurs et la signature réussit.
    
- Si l’UPN unique de chaque forêt d’utilisateurs a été synchronisé avec l’objet désactivé associé dans la forêt de ressources, l’authentification AD FS échouerait. La règle correspondante trouve l’UPN sur l’objet dans la forêt de ressources, qui a été désactivé et n’a pas pu être utilisé pour l’authentification. 
    
## <a name="create-a-microsoft-365-organization"></a>Créer une Microsoft 365 organisation

Vous devez mettre en service une Microsoft 365 à utiliser avec votre déploiement. Pour plus d’informations, voir [Abonnements, licences,](/office365/enterprise/subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings)comptes et clients pour les offres cloud de Microsoft. 
  
## <a name="configure-active-directory-federation-services"></a>Configurer les services de fédération Active Directory

Une fois que vous avez un client, vous devez configurer les services AD FS (Active Directory Federation Services) dans chacune des forêts d’utilisateurs. Cela suppose que vous avez une adresse SIP et SMTP unique et un nom d’utilisateur principal (UPN) pour chaque forêt. AD FS est facultatif et est utilisé ici pour obtenir l' sign-on unique (SSO). La synchronisation DirSync avec mot de passe est également prise en charge et peut également être utilisée à la place d’AD FS. 
  
Seuls les déploiements avec SIP/SMTP et UPN correspondants ont été testés. Le fait de ne pas disposer de correspondances SIP/SMTP/UPN peut entraîner des fonctionnalités réduites, telles que des problèmes liés à l’intégration Exchange l' puisque l’ment SSO est en cours. 
  
À moins d’utiliser un SIP/SMTP/UPN unique pour les utilisateurs de chaque forêt, vous pouvez toujours être en butte à des problèmes DSO, quel que soit l’endroit où AD FS est déployé : 
  
- Les confiances à sens unique ou double entre les forêts ressource/utilisateur avec une batterie AD FS déployée dans chaque forêt d’utilisateurs, tous les utilisateurs partagent un domaine SIP/SMTP commun, mais un UPN unique pour chaque forêt d’utilisateurs. 
    
- Les relations d’confiance entre les forêts ressource/utilisateur avec une batterie AD FS déployée uniquement dans la forêt de ressources, tous les utilisateurs partagent un domaine SIP/SMTP commun, mais un UPN unique pour chaque forêt d’utilisateurs. 
    
En plaçant une batterie de serveurs AD FS dans chaque forêt d’utilisateurs et en utilisant un SIP/SMTP/UPN unique pour chaque forêt, nous résoudons les deux problèmes. Seuls les comptes de cette forêt d’utilisateurs spécifiques sont recherchés et correspondent lors des tentatives d’authentification. Cela vous permettra de fournir un processus d’authentification plus transparent. 
  
Ce déploiement sera un déploiement standard du Windows Server 2012 R2 AD FS et devrait fonctionner avant de continuer. Pour obtenir des instructions, [voir Comment installer AD FS 2012 R2 pour Microsoft 365](https://blogs.technet.com/b/rmilne/archive/2014/04/28/how-to-install-adfs-2012-r2-for-office-365.aspx). 
  
Une fois le déploiement déployé, vous devez modifier la règle de revendications pour qu’elle corresponde à l’ancre source sélectionnée précédemment. Dans la MMC AD FS, sous Trusts de partie de confiance, cliquez avec le bouton droit sur **Microsoft 365 Identity Platform** ou Microsoft Office 365 Identity **Platform,** puis sélectionnez Modifier les règles de **revendication.** Modifiez la première règle et modifiez ObjectSID en **employeeNumber**. 
  
![Écran Modifier les règles à forêts multiples.](../../sfbserver/media/f5d485bd-52cc-437f-ba71-217f8902056c.png)
  
## <a name="configure-aad-connect"></a>Configurer les Connecter AAD

Dans les topologies de forêt de ressources, il est nécessaire que les attributs utilisateur de la forêt de ressources et de toutes les forêts de comptes soient synchronisés dans Azure AD. Microsoft recommande qu’Azure AD Connecter synchroniser et  fusionner les identités des utilisateurs de toutes les forêts qui ont activé les comptes d’utilisateur et la forêt qui contient Skype Entreprise. Pour plus d’informations, [voir Configurer Azure AD Connecter pour Skype Entreprise et Teams](configure-azure-ad-connect.md).

Notez qu’Azure AD Connecter ne fournit pas de synchronisation sur site entre le compte et les forêts de ressources. Cela doit être configuré à l’aide Microsoft Identity Manager ou d’un produit similaire, comme décrit précédemment.
  
Lorsque vous avez terminé et qu’Azure AD Connecter fusionne, si vous regardez un objet dans le métaverse, vous devriez voir quelque chose de semblable à ce qui suit : 
  
![Écran d’objet Métaverse à forêts multiples.](../../sfbserver/media/16379880-2de3-4c43-b219-1551f5dec5f6.png)
  
Les attributs en surbrillant vert ont été fusionnés à partir Microsoft 365, le jaune est issu de la forêt d’utilisateurs et le bleu est issu de la forêt de ressources. 
  
Dans cet exemple, Azure AD Connecter a identifié la sourceAnchor et le cloudSourceAnchor de l’utilisateur et les objets de forêt de ressources de Microsoft 365, dans le cas présent 1101- l’employeeNumber sélectionné précédemment. Azure AD Connecter ont pu fusionner cet objet dans ce que vous voyez ci-dessus. 
  
Pour plus d’informations, voir Intégrer vos [répertoires](/azure/active-directory/hybrid/whatis-hybrid-identity)locaux avec Azure Active Directory . 
  
Les Connecter Azure AD doivent être installés à l’aide des valeurs par défaut, à l’exception des suivantes : 
  
1. Sign-in unique - with AD FS already deployed and working: Select **Do not configure**.
    
2. Connecter répertoires : ajoutez tous les domaines.
    
3. Identifiez les utilisateurs dans les répertoires locaux : sélectionnez les identités des **utilisateurs** dans plusieurs répertoires, puis sélectionnez les attributs **ObjectSID** et **msExchangeMasterAccountSID.**
    
4. Identifiez les utilisateurs dans Azure AD : Ancre source : sélectionnez l’attribut que vous avez choisi après avoir lu Sélectionner un attribut [sourceAnchor](/azure/active-directory/hybrid/plan-connect-design-concepts#selecting-a-good-sourceanchor-attribute), Nom d’utilisateur principal - **userPrincipalName**.
    
5.  Fonctionnalités facultatives : sélectionnez si vous avez déployé Exchange déploiement hybride.
    
    > [!NOTE]
    >  Si vous n’avez Exchange Online, il peut y avoir un problème avec les échecs OAuth lors de la découverte automatique en raison de la redirection CNAME. Pour corriger cela, vous devez définir l’URL de découverte Exchange automatique en exécutant l’cmdlet suivante à partir de Skype Entreprise Server Management Shell :
    >
    > ```powershell
    > Set-CsOAuthConfiguration -ExchangeAutoDiscoverURL https://autodiscover-s.outlook.com/autodiscover/autodiscover.svc 
    > ```
    
6.  Batterie de serveurs AD FS : sélectionnez Utiliser une batterie **Windows Server 2012 R2 AD FS** et entrez le nom du serveur AD FS.
    
7.  Terminez l’Assistant et effectuez les validations nécessaires.
    
## <a name="configure-hybrid-connectivity-for-skype-for-business-server"></a>Configurer la connectivité hybride pour Skype Entreprise Server

Suivez les meilleures pratiques pour configurer Skype Entreprise hybride. Pour plus d’informations, voir [Planifier la connectivité hybride](plan-hybrid-connectivity.md) et configurer la connectivité [hybride.](configure-hybrid-connectivity.md) 
  
## <a name="configure-hybrid-connectivity-for-exchange-server"></a>Configurer la connectivité hybride pour Exchange Server

Si nécessaire, suivez les meilleures pratiques pour configurer Exchange hybride. Pour plus d’informations, [Exchange Server déploiements hybrides.](/exchange/exchange-hybrid) 
