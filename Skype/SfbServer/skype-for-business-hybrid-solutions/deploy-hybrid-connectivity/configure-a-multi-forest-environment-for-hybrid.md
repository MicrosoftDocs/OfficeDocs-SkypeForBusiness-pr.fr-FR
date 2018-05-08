---
title: Configuration d’un environnement à forêts multiples pour un environnement hybride Skype pour les entreprises
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/17/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 960ab8a3-352d-4b18-bc01-55b35f30ca0d
description: Les sections suivantes fournissent des instructions sur la façon de configurer un environnement comprenant plusieurs forêts dans un modèle de forêt de ressources/de l’utilisateur à fournir Skype pour les fonctionnalités dans un scénario hybride.
ms.openlocfilehash: 7dfbdf8348d5bf5ec51ee33d4dbd67574c509855
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="configure-a-multi-forest-environment-for-hybrid-skype-for-business"></a>Configuration d’un environnement à forêts multiples pour un environnement hybride Skype pour les entreprises
 
Les sections suivantes fournissent des instructions sur la façon de configurer un environnement comprenant plusieurs forêts dans un modèle de forêt de ressources/de l’utilisateur à fournir Skype pour les fonctionnalités dans un scénario hybride. 
  
![Environnement multi-forêt pour une utilisation hybride](../../media/5f079435-b252-4a6a-9638-3577d55b2873.png)
  
## <a name="validate-the-forest-topology"></a>Validation de la topologie de forêt

Les forêts d’utilisateurs multiples sont prises en charge. Tenez compte des points suivants :   
  
- Pour une forêt unique d’utilisateur ou déploiement dans plusieurs forêts utilisateur, il doit exister un déploiement unique de Skype pour Business Server.
    
- Pour les versions prises en charge de Lync Server et Skype pour Business Server dans une configuration hybride, voir [pour la topologie](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md#BKMK_Topology) de [planification de la connectivité hybride entre Skype pour Business Server et Skype pour Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md).
    
- Exchange Server peut être déployé dans une ou plusieurs forêts, qui peut ou ne peuvent pas inclure la forêt contenant Skype pour Business Server. Assurez-vous que vous avez appliqué la mise à jour Cumulative le plus récent.
    
- Pour plus d’informations sur la coexistence avec Exchange Server, notamment la prise en charge critères et limitations dans différentes combinaisons de locaux et en ligne, voir [fonctionnalité prise en charge](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support) de [planifier l’intégration Skype pour les entreprises et Exchange](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md).
    
Pour plus d’informations, consultez [exigences pour Skype pour Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).
  
## <a name="user-homing-considerations"></a>Aspects relatifs à l’hébergement des utilisateurs

Skype pour les utilisateurs hébergement sur site peut avoir Exchange hébergé sur site ou en ligne. Skype pour les utilisateurs professionnels Online doit utiliser Exchange Online pour une expérience optimale ; Toutefois, cela n’est pas obligatoire. Exchange sur site n’est pas nécessaire d’implémenter Skype pour les entreprises dans les deux cas.
  
## <a name="configure-forest-trusts"></a>Configuration des approbations de forêt

Les approbations nécessaires sont des approbations transitives bidirectionnelles entre la forêt de ressources et chacune des forêts d’utilisateurs. Si vous disposez de plusieurs forêts d’utilisateurs, il est important que le routage des suffixes de noms soit activé pour chacune de ces approbations de forêt pour pouvoir utiliser l’authentification inter-forêt. Pour plus d’informations, voir [Gestion des approbations de forêt](https://technet.microsoft.com/en-us/library/cc772440.aspx). 
  
## <a name="synchronize-accounts-into-the-forest-hosting-skype-for-business"></a>Synchroniser les comptes dans la forêt hébergeant Skype pour les entreprises

Lorsque Skype pour Business Server est déployé dans une forêt (une forêt de ressources), mais permet aux utilisateurs d’un ou plusieurs autres forêts (forêts compte), les utilisateurs dans les autres forêts doivent figurer en tant qu’objets utilisateur désactivés dans la forêt où Skype pour Business Server est déployé. Un produit de gestion des identités, tels que Microsoft Identity Manager, doit être déployée et configurée pour mettre en service et synchroniser les utilisateurs à partir de forêts de comptes dans la forêt où Skype pour Business Server est déployé. Les utilisateurs doivent être synchronisées dans la forêt hébergeant Skype pour Business Server en tant qu’objets utilisateur désactivés. Les utilisateurs ne peuvent pas être synchronisés en tant qu’objets contacts Active Directory, car Azure Active Directory se connecter se synchroniseront pas correctement les contacts dans Azure AD pour une utilisation avec Skype.
  
Quel que soit toutes les configurations de forêts multiples, la forêt hébergeant Skype pour Business Server peut également fournir des fonctionnalités pour les utilisateurs autorisés qui existent dans la même forêt.
  
Pour une synchronisation correcte des identités, les attributs suivants doivent être synchronisés : 
  
|**Forêts d’utilisateurs**|**Forêts de ressources**|
|:-----|:-----|
|attribut de lien du compte choisi  <br/> |attribut de lien du compte choisi  <br/> |
|mail   <br/> |mail   <br/> |
|ProxyAddresses  <br/> |ProxyAddresses  <br/> |
|ObjectSID  <br/> |msRTCSIP-OriginatorSID  <br/> |
   
Le [choisi d’attribut de lien compte](https://azure.microsoft.com/en-us/documentation/articles/active-directory-aadconnect-design-concepts/) servira le point d’ancrage de la Source. Si vous préférez utiliser un autre attribut immuable, c’est possible, mais veillez à modifier la règle des revendications AD FS et à sélectionner l’attribut lors de la configuration d’AAD Connect.
  
Ne pas synchroniser l’UPN entre les forêts. Lors des tests, nous avons découvert qu’il fallait utiliser un UPN unique pour chaque forêt d’utilisateurs, car il est impossible d’utiliser le même UPN dans plusieurs forêts. Il reste par conséquent deux possibilités : synchroniser l’UPN ou non. 
  
-  Si l’UPN de chaque forêt d’utilisateurs n’est pas synchronisé avec l’objet désactivé associé dans la forêt de ressources, l’authentification unique sera interrompue pour au moins la première tentative de connexion (en supposant que l’utilisateur a sélectionné l’option permettant d’enregistrer le mot de passe). Dans le client Skype Entreprise, nous partons du principe que les valeurs SIP/UPN sont identiques. Étant donné que l’adresse SIP dans ce scénario est user@company.com, mais que l’UPN de l’objet activé dans la forêt est en fait user@contoso.company.com, la tentative de connexion initiale échouera et l’utilisateur sera invité à entrer ses informations d’identification. En entrant l’UPN correct/réel, la demande d’authentification sera effectuée sur les contrôleurs de domaine dans la forêt d’utilisateurs, et la connexion aboutira.
    
- Si l’UPN unique de chaque forêt d’utilisateurs a été synchronisé avec l’objet désactivé associé dans la forêt de ressources, l’authentification AD FS échouera. La règle de correspondance recherchera l’UPN principal sur l’objet dans la forêt de ressources, qui a été désactivé et ne peut être utilisé pour l’authentification. 
    
## <a name="create-an-office-365-tenant"></a>Création d’un client Office 365

Vous devez ensuite fournir un client Office 365 pour le déploiement. Pour plus d’informations, consultez les [Étapes de mise en service Office 365](https://social.technet.microsoft.com/wiki/contents/articles/22808.office-365-provisioning-steps.aspx). 
  
## <a name="configure-ad-fs"></a>Configuration des services AD FS

Une fois que vous disposez d’un client, vous devez configurer les services AD FS (Active Directory Federation Services) dans chacune des forêts d’utilisateurs. Cela suppose que vous disposez d’un SIP, d’une adresse SMTP et d’un nom d’utilisateur principal (UPN) uniques dans chaque forêt. AD FS est facultatif et est utilisé ici pour obtenir une authentification unique. DirSync avec synchronisation des mots de passe est également pris en charge et peut aussi être utilisé à la place d’AD FS. 
  
Seuls les déploiements avec SIP/SMTP et UPN correspondants ont été testés. Des SIP/SMTP/UPN divergents peuvent avoir pour résultat une perte de fonctionnalités. Vous pouvez par exemple rencontrer des problèmes avec l’authentification unique et l’intégration Exchange. 
  
Sauf si vous utilisez un SIP/SMTP/UPN unique pour les utilisateurs de chaque forêt, vous pouvez toujours exécuter dans l’authentification unique (SSO) problèmes - quel que soit l’emplacement de déploiement AD FS : 
  
- Des approbations unidirectionnelles et bidirectionnelles entre les forêts ressource/utilisateur avec une batterie de serveurs AD FS déployée dans chaque forêt utilisateur. Tous les utilisateurs partagent le même domaine SIP/SMTP mais l’UPN est unique pour chaque forêt d’utilisateur. 
    
- Des approbations bidirectionnelles entre forêts ressource/utilisateur avec une batterie de serveurs AD FS uniquement déployée dans les forêts de ressources. Tous les utilisateurs partagent le même domaine SIP/SMTP mais l’UPN est unique pour chaque forêt d’utilisateur. 
    
Pour résoudre le problème, placez une batterie de serveurs AD FS dans chaque forêt utilisateur et utilisez des SIP/SMTP/UPN uniques pour chaque forêt. Seuls les comptes de cette forêt d’utilisateurs seront pris en compte lors des tentatives d’authentification. Cela vous permettra de proposer une procédure d’authentification plus transparente. 
  
Il s’agit d’un déploiement standard de Windows Server 2012 R2 AD FS qui doit être fonctionnel avant de poursuivre. Pour plus d’informations, voir [Comment faire pour installer AD FS 2012 R2 pour Office 365](https://blogs.technet.com/b/rmilne/archive/2014/04/28/how-to-install-adfs-2012-r2-for-office-365.aspx). 
  
Une fois le déploiement effectué, vous devez modifier la règle des revendications pour qu’elle corresponde à l’ancre source précédemment sélectionnée. Dans la console MMC AD FS, dans Approbations de la partie de confiance, cliquez avec le bouton droit sur Plateforme d’identité Microsoft Office 365 puis sur Modifier les règles de revendication. Dans la première règle, modifiez l’ObjectSID en employeeNumber. 
  
![Écran de modification des règles multi-forêt](../../media/f5d485bd-52cc-437f-ba71-217f8902056c.png)
  
## <a name="configure-aad-connect"></a>Configuration d’AAD Connect

AAD Connect fusionnera les comptes entre les différentes forêts et entre les forêts et Office 365. Vous devez déployer AAD Connect dans la forêt de ressources. Ceci est nécessaire pour pouvoir synchroniser plusieurs forêts et Office 365, en l’absence de prise en charge par DirSync. 
  
AAD Connect ne synchronise pas les comptes entre forêts locales. Il utilise des connecteurs AD pour lire les objets qui sont déjà synchronisés entre les forêts locales (par FIM ou produits similaires). Il tire ensuite parti des règles de filtrage pour créer une représentation unique des objets activé et désactivé correspondants dans son métaverse, et réplique cet objet unique fusionné dans Office 365. 
  
Lorsque vous avez terminé et qu’AAD Connect est en cours de fusion, un objet examiné dans le métaverse ressemble à ceci : 
  
![Fenêtre des objets du métaverse multi-forêt](../../media/16379880-2de3-4c43-b219-1551f5dec5f6.png)
  
Les attributs surlignés en vert ont été fusionnés à partir d’Office 365, ceux en jaune proviennent de la forêt utilisateur et ceux en bleu de la forêt de ressources. 
  
Il s’agit d’un utilisateur test. Vous pouvez voir qu’AAD Connect a identifié le sourceAnchor et le cloudSourceAnchor des objets de forêts utilisateur/ressource et d’Office 365, en l’occurrence 1101, qui est l’employeeNumber précédemment sélectionné. Il a ensuite pu fusionner cet objet dans ce que vous voyez ci-dessus. 
  
Pour plus d’informations, voir [intégration des identités avec Azure Active Directory local](https://azure.microsoft.com/en-us/documentation/articles/active-directory-aadconnect/). 
  
AAD Connect doit être installé avec la plupart des valeurs par défaut, à l’exception des étapes suivantes : 
  
1.  Reconnectez-vous unique - avec AD FS déjà déployé et utilisation, sélectionnez ne pas configurer
    
2. Connecter vos annuaires - ajouter tous les domaines 
    
3.  Identifier les utilisateurs dans les annuaires locaux : sélectionnez **les identités utilisateur existent sur plusieurs annuaires** et sélectionnez attributs **ObjectSID** et **msExchangeMasterAccountSID**
    
4. Identifier les utilisateurs dans Azure AD : Source d’ancrage - sélectionnez l’attribut que vous avez choisi après avoir lu la [sélection d’un attribut sourceAnchor bonne](https://azure.microsoft.com/en-us/documentation/articles/active-directory-aadconnect-design-concepts/), nom d’utilisateur Principal - **userPrincipalName**
    
5.  Fonctionnalités facultatives - Sélectionnez si vous avez déployé ou non de Exchange hybride.
    
    > [!NOTE]
    >  Si vous ne disposez que d’Exchange Online, il peut y avoir un problème avec les échecs OAuth pendant la découverte automatique en raison d’une redirection CNAME. Pour résoudre ce problème, vous devez définir l’URL de découverte automatique Exchange en exécutant l’applet de commande suivante à partir de la Skype pour Business Server Management Shell :
  
    Set-CsOAuthConfiguration - ExchangeAutoDiscoverURLhttps://autodiscover-s.outlook.com/autodiscover/autodiscover.svc 
    
6.  Batterie de serveurs AD FS : sélectionnez **Utilisation d’une batterie de serveurs Windows Server 2012 R2 AD FS existante** et entrez le nom du serveur AD FS.
    
7.  Terminez les étapes de l’assistant et effectuez les validations nécessaires.
    
## <a name="configure-hybrid-mode-for-skype-for-business-server"></a>Configurer le mode hybrique pour Skype Entreprise Server

Suivez les meilleures pratiques pour la configuration de Skype pour un environnement hybride Business. Pour plus d’informations, voir [planifier votre déploiement hybride pour Skype pour Business Server 2015](https://technet.microsoft.com/en-us/library/jj205403.aspx)et informations de configuration, voir [configuration hybride avec Skype pour Business Online](https://technet.microsoft.com/en-us/library/jj204669.aspx). 
  
## <a name="configure-hybrid-mode-for-exchange-server"></a>Configurer le mode hybrique pour Exchange Server

Si nécessaire, suivez les meilleures pratiques pour la configuration hybride d’Exchange. Pour plus d’informations, voir [Déploiements hybrides Exchange Server](https://technet.microsoft.com/en-us/library/jj200581%28v=exchg.150%29.aspx). 
  

