---
title: Configuration d’un environnement à forêts multiples pour un environnement hybride Skype pour les entreprises
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: Les sections suivantes fournissent des instructions sur la façon de configurer un environnement comprenant plusieurs forêts dans un modèle de forêt de ressources/de l’utilisateur à fournir Skype pour les fonctionnalités dans un scénario hybride.
ms.openlocfilehash: 72c0a91c3a5a90b4ec83eb5f71a5601ccfb48bb1
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295361"
---
# <a name="configure-a-multi-forest-environment-for-hybrid-skype-for-business"></a>Configuration d’un environnement à forêts multiples pour un environnement hybride Skype pour les entreprises
 
Les sections suivantes fournissent des instructions sur la façon de configurer un environnement comprenant plusieurs forêts dans un modèle de forêt de ressources/de l’utilisateur à fournir Skype pour les fonctionnalités dans un scénario hybride. 
  
![Environnement multi-forêt pour une utilisation hybride](../../sfbserver/media/5f079435-b252-4a6a-9638-3577d55b2873.png)
  
## <a name="validate-the-forest-topology"></a>Valider la topologie à forêt

Les forêts d’utilisateurs multiples sont prises en charge. Tenez compte des points suivants : 
  
- Pour un utilisateur unique forêt ou un déploiement à forêts multiples utilisateur, il doit exister un déploiement unique de Skype pour Business Server.
    
- Pour les versions prises en charge de Lync Server et Skype pour Business Server dans une configuration hybride, voir [pour la topologie](plan-hybrid-connectivity.md#BKMK_Topology) de [planification de la connectivité hybride entre Skype pour Business Server et Office 365](plan-hybrid-connectivity.md).
    
- Exchange Server peut être déployé dans une ou plusieurs forêts, qui peut ou ne peuvent pas inclure la forêt contenant Skype pour Business Server. Assurez-vous que vous avez appliqué la mise à jour Cumulative le plus récent.
    
- Pour plus de détails sur la coexistence avec Exchange Server, notamment sur les critères de prise en charge et les limitations de plusieurs combinaisons locales et en ligne, reportez-vous à la rubrique [Fonctionnalités prises en charge](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support) dans [Plan to integrate Skype for Business and Exchange](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md).
    
Pour plus d’informations, reportez-vous à la [configuration système requise](../plan/system-requirements.md).
  
## <a name="user-homing-considerations"></a>Aspects relatifs à l’hébergement des utilisateurs

Skype pour les utilisateurs hébergement sur site peut avoir Exchange hébergé sur site ou en ligne. Skype pour les utilisateurs professionnels Online doit utiliser Exchange Online pour une expérience optimale ; Toutefois, cela n’est pas obligatoire. Exchange sur site n’est pas nécessaire d’implémenter Skype pour les entreprises dans les deux cas.
  
## <a name="configure-forest-trusts"></a>Configurer les approbations de forêt

Les approbations nécessaires sont des approbations transitives bidirectionnelles entre la forêt de ressources et chacune des forêts d’utilisateurs. Si vous disposez de plusieurs forêts d’utilisateurs, il est important que le routage des suffixes de noms soit activé pour chacune de ces approbations de forêt pour pouvoir utiliser l’authentification inter-forêt. Pour obtenir des instructions, reportez-vous à [Gestion des approbations de forêt](https://technet.microsoft.com/en-us/library/cc772440.aspx). 
  
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
   
L’[attribut de lien de compte choisi](https://azure.microsoft.com/en-us/documentation/articles/active-directory-aadconnect-design-concepts/) sera utilisé comme ancre source. Si vous avez un attribut différents et immuable que vous préférez utiliser, vous devez ; Veillez à modifier la règle basée sur les revendications AD FS, puis sélectionnez l’attribut lors de la configuration DAS se connecter.
  
Ne pas synchroniser l’UPN entre les forêts. Lors des tests, nous avons découvert qu’il fallait utiliser un UPN unique pour chaque forêt d’utilisateurs, car il est impossible d’utiliser le même UPN dans plusieurs forêts. Il reste par conséquent deux possibilités : synchroniser l’UPN ou non. 
  
- Si l’UPN unique à partir de chaque forêt d’utilisateur n’a pas été synchronisé à l’objet associé désactivé dans la forêt de ressources, authentification unique (SSO) doit être fractionné au moins la tentative de connexion initiale (en supposant que l’utilisateur a sélectionné l’option Enregistrer le mot de passe). Dans Skype pour client d’entreprise, nous partons du principe que les valeurs SIP/UPN sont les mêmes. Étant donné que l’adresse SIP dans ce scénario est user@company.com, mais que l’UPN de l’objet activé dans la forêt est en fait user@contoso.company.com, la tentative de connexion initiale échouera et l’utilisateur sera invité à entrer ses informations d’identification. En entrant l’UPN correct/réel, la demande d’authentification sera effectuée sur les contrôleurs de domaine dans la forêt d’utilisateurs, et la connexion aboutira.
    
- Si l’UPN unique à partir de chaque forêt d’utilisateurs a été synchronisé avec l’objet désactivé associé dans la forêt de ressources, l’authentification AD FS échouent. La règle de correspondance recherchera l’UPN principal sur l’objet dans la forêt de ressources, qui a été désactivé et ne peut être utilisé pour l’authentification. 
    
## <a name="create-an-office-365-tenant"></a>Création d’un client Office 365

Vous devez ensuite fournir un client Office 365 pour le déploiement. Pour plus d’informations, consultez [abonnements, licences et des comptes et clients pour les offres de cloud de Microsoft](https://docs.microsoft.com/en-us/office365/enterprise/subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings). 
  
## <a name="configure-active-directory-federation-services"></a>Configurer Active Directory Federation Services

Une fois que vous avez un client, vous devez configurer Active Directory Federation Services (ADFS) dans chacune des forêts d’utilisateurs. Cela suppose que vous disposez d’un SIP, d’une adresse SMTP et d’un nom d’utilisateur principal (UPN) uniques dans chaque forêt. AD FS est facultatif et est utilisé ici pour obtenir d’authentification unique (SSO). DirSync avec synchronisation des mots de passe est également pris en charge et peut aussi être utilisé à la place d’AD FS. 
  
Uniquement les déploiements à l’aide de SIP/SMTP et UPN correspondants ont été testés. Sans devoir correspondants SIP/SMTP/UPN risque d’utilisation avec fonctionnalités réduite, tels que des problèmes liés à l’intégration d’Exchange et l’authentification unique. 
  
Sauf si vous utilisez un SIP/SMTP/UPN unique pour les utilisateurs de chaque forêt, vous pouvez toujours exécuter des problèmes d’authentification unique, quel que soit l’emplacement de déploiement AD FS : 
  
- Des approbations unidirectionnelles et bidirectionnelles entre les forêts ressource/utilisateur avec une batterie de serveurs AD FS déployée dans chaque forêt utilisateur. Tous les utilisateurs partagent le même domaine SIP/SMTP mais l’UPN est unique pour chaque forêt d’utilisateur. 
    
- Des approbations bidirectionnelles entre forêts ressource/utilisateur avec une batterie de serveurs AD FS uniquement déployée dans les forêts de ressources. Tous les utilisateurs partagent le même domaine SIP/SMTP mais l’UPN est unique pour chaque forêt d’utilisateur. 
    
Pour résoudre le problème, placez une batterie de serveurs AD FS dans chaque forêt utilisateur et utilisez des SIP/SMTP/UPN uniques pour chaque forêt. Seuls les comptes de cette forêt d’utilisateurs seront pris en compte lors des tentatives d’authentification. Cela vous permettra de proposer une procédure d’authentification plus transparente. 
  
Il s’agit d’un déploiement standard de Windows Server 2012 R2 AD FS qui doit être fonctionnel avant de poursuivre. Pour obtenir des instructions, reportez-vous à la rubrique [Installation d’AD FS 2012 R2 pour Office 365](https://blogs.technet.com/b/rmilne/archive/2014/04/28/how-to-install-adfs-2012-r2-for-office-365.aspx). 
  
Une fois le déploiement effectué, vous devez modifier la règle des revendications pour qu’elle corresponde à l’ancre source précédemment sélectionnée. Dans la console MMC AD FS, sous Relying Party Trusts, avec le bouton droit de **Plateforme d’identité Microsoft Office 365**, puis cliquez sur **Modifier les règles de revendication**. Modifiez la première règle et ObjectSID **EmployeeNumber**. 
  
![Écran de modification des règles multi-forêt](../../sfbserver/media/f5d485bd-52cc-437f-ba71-217f8902056c.png)
  
## <a name="configure-aad-connect"></a>Configuration d’AAD Connect

AAD Connect fusionnera les comptes entre les différentes forêts et entre les forêts et Office 365. Vous devez déployer AAD Connect dans la forêt de ressources. Ceci est nécessaire pour pouvoir synchroniser plusieurs forêts et Office 365, en l’absence de prise en charge par DirSync. 
  
AAD Connect ne synchronise pas les comptes entre forêts locales. Il utilise des connecteurs AD pour lire les objets qui sont déjà synchronisés entre les forêts locales (par FIM ou produits similaires). Il tire ensuite parti des règles de filtrage pour créer une représentation unique des objets activé et désactivé correspondants dans son métaverse, et réplique cet objet unique fusionné dans Office 365. 
  
Lorsque vous avez terminé et qu’AAD Connect est en cours de fusion, un objet examiné dans le métaverse ressemble à ceci : 
  
![Fenêtre des objets du métaverse multi-forêt](../../sfbserver/media/16379880-2de3-4c43-b219-1551f5dec5f6.png)
  
Vert en surbrillance attributs ont été fusionnées à partir d’Office 365, le jaune sont à partir de la forêt d’utilisateurs, et le bleu sont à partir de la forêt de ressources. 
  
Il s’agit d’un utilisateur test, et vous pouvez voir que DAS se connecter a identifié la sourceAnchor et le cloudSourceAnchor à partir de l’utilisateur et les objets de forêt de ressources d’Office 365, dans notre cas 1101, c'est-à-dire employeeNumber sélectionnée précédemment. Il était puis en mesure de fusionner cet objet dans ce que vous voyez ci-dessus. 
  
Pour plus d’informations, voir [répertoires intégrer votre locale avec Azure Active Directory](https://azure.microsoft.com/en-us/documentation/articles/active-directory-aadconnect/). 
  
Connexion DAS doivent être installé à l’aide des valeurs par défaut, à l’exception des suivantes : 
  
1. Single sign-in - avec AD FS déjà déployé et travail : sélectionnez **ne pas configurer**.
    
2. Connecter vos annuaires : ajouter tous les domaines.
    
3. Identifier les utilisateurs dans les annuaires locaux : sélectionnez **les identités utilisateur existent dans plusieurs répertoires**, puis sélectionnez les attributs **ObjectSID** et **msExchangeMasterAccountSID** .
    
4. Identifier les utilisateurs dans Azure AD : ancrage Source : sélectionnez l’attribut que vous avez choisi après avoir lu la [sélection d’un attribut sourceAnchor bonne](https://azure.microsoft.com/en-us/documentation/articles/active-directory-aadconnect-design-concepts/), nom d’utilisateur Principal - **userPrincipalName**.
    
5.  Fonctionnalités facultatives : indiquez si vous avez Exchange hybride est déployé.
    
    > [!NOTE]
    >  Si vous ne disposez que d’Exchange Online, il peut y avoir un problème avec les échecs OAuth pendant la découverte automatique en raison d’une redirection CNAME. Pour résoudre ce problème, vous devez définir l’URL de découverte automatique Exchange en exécutant l’applet de commande suivante à partir de la Skype pour Business Server Management Shell :
  
    Set-CsOAuthConfiguration - ExchangeAutoDiscoverURL https://<span>autodiscover-s.outlook.com/autodiscover/autodiscover.svc 
    
6.  Batterie de serveurs AD FS : sélectionnez **Utilisation d’une batterie de serveurs Windows Server 2012 R2 AD FS existante** et entrez le nom du serveur AD FS.
    
7.  Terminez les étapes de l’assistant et effectuez les validations nécessaires.
    
## <a name="configure-hybrid-connectivity-for-skype-for-business-server"></a>Configurer la connectivité hybride pour Skype pour Business Server

Suivez les meilleures pratiques pour la configuration de Skype pour un environnement hybride Business. Pour plus d’informations, voir [planification de la connectivité hybride](plan-hybrid-connectivity.md) et de [connectivité de configuration hybride](configure-hybrid-connectivity.md). 
  
## <a name="configure-hybrid-connectivity-for-exchange-server"></a>Configurer la connectivité hybride pour Exchange Server

Si nécessaire, suivez les meilleures pratiques pour la configuration hybride d’Exchange. Pour plus d’informations, voir [Déploiements hybrides Exchange Server](https://technet.microsoft.com/en-us/library/jj200581%28v=exchg.150%29.aspx). 
  

