---
title: Topologies de Skype Entreprise prises en charge avec l'authentification moderne
ms.author: tracyp
author: MSFTTracyP
manager: serdars
ms.date: 12/4/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: tracyp
ms.assetid: 258430b0-574a-47fb-90b7-54ee8996b2ec
description: Cet article établit la liste des topologies en ligne et en local prises en charge avec l'authentification moderne dans Skype Entreprise, et des fonctionnalités de sécurité qui s'appliquent à chacune des topologies.
ms.openlocfilehash: a6be001bf1aeeeba9823c291ee9726c33ec9009a
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/05/2018
---
# <a name="skype-for-business-topologies-supported-with-modern-authentication"></a>Topologies de Skype Entreprise prises en charge avec l'authentification moderne
 
Cet article établit la liste des topologies en ligne et en local prises en charge avec l'authentification moderne dans Skype Entreprise, et des fonctionnalités de sécurité qui s'appliquent à chacune des topologies.
  
## <a name="modern-authentication-in-skype-for-business"></a>Authentification moderne dans Skype Entreprise

Skype Entreprise peut tirer profit des avantages apportés par l'authentification moderne. Étant donné que Skype Entreprise travaille en étroite collaboration avec Exchange, le comportement de connexion que les utilisateurs de Skype Entreprise verront sera également affecté par le statut de MA (authentification moderne) d'Exchange. Ceci s'applique également si vous possédez un hybride de Skype Entreprise à domaine séparé. Cela représente beaucoup d'éléments amovibles, mais l'objectif est de présenter une liste des topologies prises en charge facile à visualiser.
  
En ce qui concerne Skype Entreprise, Skype Entreprise Online, Exchange Server et Exchange Online, quelles topologies sont prises en charge avec MA ?
  
<!--  > [!TIP] > Not sure what Modern Authentication even is? No worries.  This Skype for Business article  4e6a99cd-7859-4062-8a30-5ac79ba36b52  explains it in the first paragraphs. --> 
  
### <a name="supported-ma-topologies-in-skype-for-business"></a>Topologies de MA prises en charge dans Skype Entreprise

Il existe potentiellement deux applications serveur, et deux charges de travail Office 365, impliquées dans les topologies Skype Entreprise utilisées par MA.
  
- Skype Entreprise Server 2015 (CU 5) local
    
- Skype Entreprise Online (SFBO)
    
- Exchange Server local
    
- Exchange Server Online (EXO)
    
L'autre aspect important de MA est de savoir où l'authentification (authN) et l'autorisation (authZ) des utilisateurs auront lieu. Les deux options possibles sont les suivantes :
  
- Azure AD, en ligne dans le cloud Microsoft
    
- Serveur d'Active Directory Federation (ADFS) local
    
Voici ce à quoi cela peut ressembler : EXO et SFBO dans le cloud et Azure AD, et Exchange Server (EXCH) et Skype Entreprise Server 2015 (SFB) local.
  
![Exemple de l'ensemble des applications (Exchange et Skype Entreprise), des charges de travail (EXO et SFBO) et des serveurs d'autorisation (ADFS et evoSTS) qui peuvent être impliqués lors de l'activation de MA.](../../media/18a3b451-1e64-40fc-b47f-7ce9587814bb.PNG)
  
Voici les topologies prises en charge. Veuillez noter la légende du graphique :
  
- Si l’icône est grisée ou gris, il n’est pas utilisée dans le scénario.
    
- EXO correspond à Exchange Online.
    
- SFBO correspond à Skype Entreprise Online.
    
- EXCH correspond à Exchange local.
    
- SFB correspond à Skype Entreprise local.
    
- Les serveurs d'autorisation sont représentés par des triangles, par exemple : Azure AD est un triangle avec un nuage derrière.
    
- Les flèches indiquent les serveurs d'autorisation qui seront utilisés lorsque des clients tenteront d'atteindre les ressources du serveur indiqué.
    
Pour commencer, nous allons aborder l'authentification moderne avec Skype Entreprise dans les topologies locales uniquement et dans le cloud uniquement.
  
> [!IMPORTANT]
> Êtes-vous prêt à configurer l’authentification modernes dans Skype pour entreprise en ligne ? La procédure d’activation de cette fonctionnalité est [ici](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx). 
  
|Nom de la topologie  <br/> |Exemple  <br/> |Description%  <br/> |Pris en charge  <br/> |
|:-----|:-----|:-----|:-----|
|Dans le cloud uniquement  <br/> |![Prise en charge de la topologie SFB avec MA, cloud uniquement.](../../media/4d19b47f-8257-4a6f-9dab-0755206f7c52.PNG)Utilisateurs hébergés/boîtes aux lettres situées : en ligne   <br/> |MA est activée pour EXO et SFBO.  <br/> Le serveur d'autorisation est donc Azure AD.  <br/> |Plusieurs facteurs d’authentification (AMF), authentification (CBA), l’accès conditionnel (CA) basée sur le certificat Client / Mobile Application Management (MAM) avec Intune. \*  <br/> |
|En local uniquement  <br/> |![Prise en charge de la topologie SFB avec MA, sur site uniquement.](../../media/9773e9a5-7cd6-41ef-940b-c4386c9fce20.PNG)Utilisateurs hébergés/boîtes aux lettres situées : en local  <br/> |MA est activée pour SFB local.  <br/> Le serveur d'autorisation est donc ADFS.  <br/> Pour plus d’informations, consultez [cet article.](https://technet.microsoft.com/en-us/library/mt710548.aspx) <br/> |MFA (Windows Desktop uniquement - les mobiles clients ne sont pas pris en charge). Aucune fonctionnalité d'intégration Exchange.  <br/> |
   
> [!IMPORTANT]
> Il est recommandé que l'état de MA soit le même pour Skype Entreprise et Exchange (ainsi que pour leurs homologues en ligne) afin de réduire le nombre d'invites. 
  
Les topologies mixtes impliquent des combinaisons d'hybrides de SFB à domaine séparé. Les topologies mixtes actuellement prises en charge sont les suivantes :
  
|Nom de la topologie  <br/> |Exemple  <br/> |Description%  <br/> |Pris en charge   <br/> |
|:-----|:-----|:-----|:-----|
|Mixte 1  <br/> |![Prise en charge de la topologie SFB avec MA, mixte 1 (EXO + SFB).](../../media/7b2e607a-c83a-4bb3-9b48-a43566516129.PNG)           <br/> Utilisateurs hébergés/boîtes aux lettres situées : EXO et SFB  <br/> |MA n'est pas activée pour SFB, aucune fonctionnalité MA SFB n'est disponible pour cette topologie.  <br/> |Aucune fonctionnalité MA pour SFB.  <br/> |
|Mixte 2  <br/> |![Prise en charge de la topologie mixte MA-S4B 2, SFBO plus MA exécuté avec EXCH sur site.](../../media/247a985d-39cd-4c16-a19e-b8b65207d82e.PNG)           <br/> Utilisateurs hébergés/boîtes aux lettres situées : EXCH et SFBO  <br/> |MA concerne sur SFBO uniquement. Le serveur d’autorisation est AD Azure pour les utilisateurs hébergés dans SFBO, mais Active Directory pour EXCH sur site.  <br/> |Autorité de certification AMF, CBA, / MAM avec Intune.\*  <br/> |
|Mixte 3  <br/> |![Prise en charge de MA avec SFB, EXO avec MA local, plus EXCH et SFB sur site.](../../media/772dc261-c041-4a96-90d0-fd0b5124decf.PNG)           <br/> Utilisateurs hébergés/boîtes aux lettres situées : EXO + SFB ou EXCH + SFB  <br/> |Aucune fonctionnalité MA SFB n'est disponible pour cette topologie  <br/> |Aucune fonctionnalité MA pour SFB.  <br/> |
|Mixte 4  <br/> |![Prise en charge de MA avec SFB, SFBO avec MA local, plus EXCH et SFB](../../media/8971bfaf-961f-476c-b16e-5418d1fa0a6d.PNG)           <br/> Utilisateurs hébergés/boîtes aux lettres situées : EXCH + SFBO ou EXCH + SFB   <br/> |MA est activé pour le SFBO, le serveur d’autorisation AD Azure pour les utilisateurs hébergés dans SFBO. Utilisateurs sur prem SFB et EXO utilisent Active Directory.  <br/> |Autorité de certification AMF, CBA, / MAM avec Intune uniquement aux utilisateurs en ligne.\*  <br/> |
|Mixte 5  <br/> |![Prise en charge de MA dans SFB, EXO avec MA, SFBO avec MA, EXCH et SFB sur site.](../../media/ecc366cf-1a7b-4ad1-bf8e-57111b8ad94f.PNG)           <br/> Utilisateurs hébergés/boîtes aux lettres situées : EXO + SFBO, EXO + SFB, EXCH + SFBO ou EXCH + SFB  <br/> |MA est activé dans EXO et SFBO, par conséquent que le serveur d’autorisation est AD Azure pour les utilisateurs hébergés dans SFBO ; utilisateurs sur prem EXCH et SFB utilisent Active Directory.  <br/> |Autorité de certification AMF, CBA, / MAM avec Intune uniquement aux utilisateurs en ligne.\*  <br/> |
|6 mixte  <br/> |![Dans une topologie Mixte 6, l'authentification moderne est activée dans les quatre emplacements possibles, situation idéale en matière d'authentification moderne.](../../media/8de21756-9152-466d-a706-58b258e2271c.png)           <br/> Utilisateurs hébergés/boîtes aux lettres situées : EXO + SFBO, EXO + SFB, EXCH + SFBO ou EXCH + SFB  <br/> |MA est sur partout, le serveur d’autorisation AD Azure pour tous les utilisateurs. (en ligne et sur site)  <br/>  Veuillez consulter [https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview) pour les étapes de déploiement. <br/> |AMF, CBA et autorité de certification/MAM (via Intune) pour tous les utilisateurs.  <br/> |
   
\*-AMF inclut le bureau Windows, MAC, iOS, Android périphériques et téléphones de Windows ; CBA inclut le bureau Windows, périphériques iOS ou Android ; Autorité de certification/MAM avec Intune, inclut des appareils Android et iOS. 
  
> [!IMPORTANT]
> Il est très important de noter que les utilisateurs peuvent recevoir **plusieurs invites** dans certains cas, notamment lorsque l’état de MA n’est pas le même sur toutes les ressources serveur que les clients ont besoin et demandent, comme c’est le cas avec toutes les versions des topologies mixtes.

> [!IMPORTANT]
> Notez également que dans certains cas (mixte 1, 3 et 5 en particulier) une clé de Registre [AllowADALForNonLynIndependentOfLync](https://support.microsoft.com/en-us/help/3082803/info-about-the-allowadalfornonlyncindependentoflync-setting-in-skype-for-business,-lync-2013,-and-exchange-online) doit être définie pour une configuration correcte des Clients de bureau Windows.
  

