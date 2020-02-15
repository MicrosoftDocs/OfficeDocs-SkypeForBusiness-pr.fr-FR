---
title: Topologies Skype entreprise prises en charge avec l’authentification moderne
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: tracyp
ms.assetid: 258430b0-574a-47fb-90b7-54ee8996b2ec
description: Cet article répertorie les topologies en ligne et locales prises en charge avec l’authentification moderne dans Skype entreprise, ainsi que les fonctionnalités de sécurité qui s’appliquent à chaque topologie.
ms.openlocfilehash: b23c2081833b43f0f734febc0b18356abf63506e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043756"
---
# <a name="skype-for-business-topologies-supported-with-modern-authentication"></a>Topologies Skype entreprise prises en charge avec l’authentification moderne
 
Cet article répertorie les topologies en ligne et locales prises en charge avec l’authentification moderne dans Skype entreprise, ainsi que les fonctionnalités de sécurité qui s’appliquent à chaque topologie.
  
## <a name="modern-authentication-in-skype-for-business"></a>Authentification moderne dans Skype entreprise

Skype entreprise peut tirer parti des avantages de la sécurité de l’authentification moderne. Étant donné que Skype entreprise travaille en étroite collaboration avec Exchange, le comportement de connexion des utilisateurs du client Skype entreprise s’affichera également en fonction de l’état de l’agent de gestion Exchange. Cela s’applique également si vous disposez d’un hybride de domaine mixte Skype entreprise. Il s’agit d’un grand nombre de pièces mobiles, mais l’objectif ici est une liste facile à visualiser des topologies prises en charge.
  
Skype entreprise, Skype entreprise Online, Exchange Server et Exchange Online étant des topologies prises en charge par l’agent de gestion ?
  
<!--  > [!TIP] > Not sure what Modern Authentication even is? No worries.  This Skype for Business article  4e6a99cd-7859-4062-8a30-5ac79ba36b52  explains it in the first paragraphs. --> 
  
### <a name="supported-ma-topologies-in-skype-for-business"></a>Topologies MA prises en charge dans Skype entreprise

Il existe potentiellement deux applications serveur, et deux charges de travail Office 365, impliquées dans des topologies Skype entreprise utilisées par MA.
  
- Skype entreprise Server (CU 5) en local
    
- Skype entreprise Online (SFBO)
    
- Exchange Server local
    
- Exchange Server Online (EXO)
    
Une autre partie importante de l’agent de stockage est de savoir où les utilisateurs de l’authentification (Authn) et de l’autorisation (auth) des utilisateurs auront lieu. Les deux options sont les suivantes :
  
- Azure AD, en ligne dans le Cloud Microsoft
    
- Active Directory Federation Server (ADFS) en local
    
Par conséquent, il ressemble un peu à cela, avec EXO et SFBO dans le Cloud avec Azure AD, et Exchange Server (EXCH) et Skype entreprise Server (SFB) sur-local.
  
![Un exemple de toutes les applications (Exchange et Skype entreprise) et charges de travail (EXO et SFBO), ainsi que des deux serveurs d’autorisation (ADFS et evoSTS) qui peuvent être impliqués lors de l’activation de MA.](../../media/18a3b451-1e64-40fc-b47f-7ce9587814bb.PNG)
  
Voici les topologies prises en charge. Veuillez noter la clé des graphiques :
  
- Si l’icône est grisée ou grisée, elle n’est pas utilisée dans le scénario.
    
- EXO est Exchange Online.
    
- SFBO est Skype entreprise online.
    
- EXCH est Exchange sur site.
    
- SFB est Skype entreprise en local.
    
- Les serveurs d’autorisation sont représentés par des triangles, par exemple, Azure AD est un triangle avec un nuage derrière.
    
- Des flèches pointent sur le serveur d’autorisation qui sera utilisé lorsque les clients tenteront d’atteindre la ressource de serveur spécifiée.
    
Tout d’abord, nous allons parler de MA avec Skype entreprise dans les topologies locales uniquement ou en nuage uniquement.
  
> [!IMPORTANT]
> Êtes-vous prêt à configurer l’authentification moderne dans Skype entreprise Online ? Les étapes d’activation de cette fonctionnalité sont indiquées [ici](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx). 
  
|Nom de la topologie  <br/> |Exemple  <br/> |Description  <br/> |Pris en charge  <br/> |
|:-----|:-----|:-----|:-----|
|Cloud uniquement  <br/> |![Prise en charge de SFB avec MA topologie, Cloud uniquement.](../../media/4d19b47f-8257-4a6f-9dab-0755206f7c52.PNG)Utilisateurs hébergés/boîtes aux lettres situées : en ligne  <br/> |MA est activée pour EXO et SFBO.  <br/> Par conséquent, le serveur d’autorisation est Azure AD.  <br/> |Authentification multifacteur (MFA), authentification basée sur les certificats clients (CBA), accès conditionnel (CA)/mobile de gestion des applications (MAM) avec Intune. \*  <br/> |
|Local uniquement  <br/> |![Prise en charge de SFB avec MA topologie, locale uniquement.](../../media/9773e9a5-7cd6-41ef-940b-c4386c9fce20.PNG)Utilisateurs hébergés/boîtes aux lettres situées : en local  <br/> |MA est activée pour SFB en local.  <br/> Par conséquent, le serveur d’autorisation est ADFS.  <br/> Pour plus d’informations sur la configuration, reportez-vous à [cet article.](https://technet.microsoft.com/library/mt710548.aspx) <br/> |MFA (Windows Desktop uniquement-clients mobiles non pris en charge). Aucune fonctionnalité d’intégration Exchange.  <br/><p> **Nous ne recommandons pas cette approche. Veuillez consulter les éléments suivants :**[https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview)<p/> |
   
> [!IMPORTANT]
> Il est recommandé que l’état de MA soit identique pour Skype entreprise et Exchange (et leurs homologues en ligne) afin de réduire le nombre d’invites. 
  
Les topologies mixtes impliquent des combinaisons de hybrides de domaine SFB. Voici les topologies mixtes actuellement prises en charge :
  
|Nom de la topologie  <br/> |Exemple  <br/> |Description  <br/> |Pris en charge  <br/> |
|:-----|:-----|:-----|:-----|
|Mixte 1  <br/> |![Prise en charge de SFB avec MA topologie, mixed 1 (EXO + SFB).](../../media/7b2e607a-c83a-4bb3-9b48-a43566516129.PNG)           <br/> Utilisateurs hébergés/boîtes aux lettres situées : EXO et SFB  <br/> |MA n’est pas activée pour SFB ; aucune fonctionnalité MA SFB disponible dans cette topologie.  <br/> |Aucune fonctionnalité MA pour SFB.  <br/> |
|Mixte 2  <br/> |![Prise en charge de MA avec S4B Mixed Topology 2, SFBO plus MA Working with EXCH-local.](../../media/247a985d-39cd-4c16-a19e-b8b65207d82e.PNG)           <br/> Utilisateurs hébergés/boîtes aux lettres situées : EXCH et SFBO  <br/> |MA est activée pour SFBO uniquement. Le serveur d’autorisation est Azure AD pour les utilisateurs hébergés dans SFBO, mais AD pour EXCH en local.  <br/> |MFA, CBA, CA/MAM avec Intune.\*  <br/> |
|Mixte 3  <br/> |![Prise en charge de MA avec SFB, EXO avec MA sur, plus EXCH et SFB sur site.](../../media/772dc261-c041-4a96-90d0-fd0b5124decf.PNG)           <br/> Utilisateurs hébergés/boîtes aux lettres situées : EXO + SFB ou EXCH + SFB  <br/> |Aucune fonctionnalité MA SFB disponible dans cette topologie  <br/> |Aucune fonctionnalité MA pour SFB.  <br/> |
|Mixte 4  <br/> |![Prise en charge de MA avec SFB, SFBO avec MA sur, plus EXCH et SFB.](../../media/8971bfaf-961f-476c-b16e-5418d1fa0a6d.PNG)           <br/> Utilisateurs hébergés/boîtes aux lettres situées : EXCH + SFBO ou EXCH + SFB  <br/> |MA est activée pour SFBO, le serveur d’autorisation est donc Azure AD pour les utilisateurs hébergés dans SFBO. Les utilisateurs local dans SFB et EXO utilisent AD.  <br/> |MFA, CBA, CA/MAM avec Intune pour les utilisateurs en ligne uniquement.\*  <br/> |
|Mixte 5  <br/> |![Prise en charge de MA dans SFB, EXO avec MA et SFBO avec MA, et EXCH et SFB sur site.](../../media/ecc366cf-1a7b-4ad1-bf8e-57111b8ad94f.PNG)           <br/> Utilisateurs hébergés/boîtes aux lettres situées : EXO + SFBO, EXO + SFB, EXCH + SFBO ou EXCH + SFB  <br/> |MA est activée à la fois dans EXO et SFBO, le serveur d’autorisation est donc Azure AD pour les utilisateurs hébergés dans SFBO ; les utilisateurs local de EXCH et SFB utilisent AD.  <br/> |MFA, CBA, CA/MAM avec Intune pour les utilisateurs en ligne uniquement.\*  <br/> |
|Mixte 6  <br/> |![Dans une topologie mixte 6, l’authentification moderne est activée dans les quatre emplacements possibile, le idéale idéal en ce qui concerne l’authentification moderne.](../../media/8de21756-9152-466d-a706-58b258e2271c.png)           <br/> Utilisateurs hébergés/boîtes aux lettres situées : EXO + SFBO, EXO + SFB, EXCH + SFBO ou EXCH + SFB  <br/> |MA est sur tout le monde, le serveur d’autorisation est donc Azure AD pour tous les utilisateurs. (en ligne et en local)  <br/>  Consultez la [https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview) section relative aux étapes de déploiement. <br/> |MFA, CBA et CA/MAM (via Intune) pour tous les utilisateurs.  <br/> |
   
\*-MFA inclut le bureau Windows, MAC, iOS, les appareils Android et les téléphones Windows ; CBA inclut les appareils Windows de bureau, iOS et Android ; CA/MAM avec Intune, comprend les appareils Android et iOS. 
  
> [!IMPORTANT]
> Il est très important de noter que les utilisateurs peuvent afficher **plusieurs invites** dans certains cas, notamment lorsque l’état de l’agent de démarrage n’est pas le même pour toutes les ressources serveur dont les clients peuvent avoir besoin et, comme c’est le cas avec toutes les versions des topologies mixtes.

> [!IMPORTANT]
> Notez également que dans certains cas (mixte 1, 3 et 5 spécifiquement) une clé de Registre [AllowADALForNonLynIndependentOfLync](https://support.microsoft.com/help/3082803/info-about-the-allowadalfornonlyncindependentoflync-setting-in-skype-for-business,-lync-2013,-and-exchange-online) doit être définie pour une configuration correcte pour les clients de bureau Windows.
  

