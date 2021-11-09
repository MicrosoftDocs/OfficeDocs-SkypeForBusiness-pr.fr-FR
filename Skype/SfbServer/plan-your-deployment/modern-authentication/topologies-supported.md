---
title: Topologies Skype Entreprise prises en charge avec l’authentification moderne
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.custom: tracyp
ms.assetid: 258430b0-574a-47fb-90b7-54ee8996b2ec
description: Cet article répertorie les topologies en ligne et sur site qui sont pris en charge avec l’authentification moderne dans Skype Entreprise, ainsi que les fonctionnalités de sécurité qui s’appliquent à chaque topologie.
ms.openlocfilehash: ed6710e0f25e946e8cb9e7034300bd450dd07baa
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60835072"
---
# <a name="skype-for-business-topologies-supported-with-modern-authentication"></a>Topologies Skype Entreprise prises en charge avec l’authentification moderne

Cet article répertorie les topologies en ligne et sur site qui sont pris en charge avec l’authentification moderne dans Skype Entreprise, ainsi que les fonctionnalités de sécurité qui s’appliquent à chaque topologie.

## <a name="modern-authentication-in-skype-for-business"></a>Authentification moderne dans Skype Entreprise

Skype Entreprise tirer parti des avantages de sécurité de l’authentification moderne. Étant donné Skype Entreprise fonctionne en étroite collaboration avec Exchange, le comportement de connexion Skype Entreprise les utilisateurs clients seront également affectés par l’état de l’Exchange. Cela s’applique également si vous avez un Skype Entreprise hybride à domaine partagé. Il s’agit d’un grand nombre de composants mobiles, mais le but ici est de visualiser facilement la liste des topologies pris en charge.

Quelles topologies sont Skype Entreprise, Skype Entreprise en ligne, Exchange Server et Exchange en ligne, quelles topologies sont pris en charge avec MA ?

<!--  > [!TIP] > Not sure what Modern Authentication even is? No worries.  This Skype for Business article  4e6a99cd-7859-4062-8a30-5ac79ba36b52  explains it in the first paragraphs. -->

### <a name="supported-ma-topologies-in-skype-for-business"></a>Topologies MA pris en charge dans Skype Entreprise

Il existe potentiellement deux applications serveur et deux charges Microsoft 365 ou Office 365 charges de travail, impliquées dans Skype Entreprise topologies utilisées par MA.

- Skype Entreprise serveur local (CU 5)

- Skype Entreprise online (SFBO)

- Exchange serveur local

- Exchange server online (EXO)

Une autre partie importante de MA est de savoir où l’authentification (authN) et l’autorisation (authZ) des utilisateurs auront lieu. Les deux options sont :

- Azure AD, en ligne dans Microsoft Cloud

- Serveur ADFS (Active Directory Federation Server) local

Il ressemble donc un peu à ceci, avec EXO et SFBO dans le cloud avec Azure AD, et Exchange Server (EXCH) et Skype Entreprise server (SFB) sur site.

![Exemple de toutes les applications (Exchange et Skype Entreprise) et charges de travail (EXO et SFBO), ainsi que des deux serveurs d’autorisation (ADFS et evoSTS) qui peuvent être impliqués lors de l’utilisation de MA.](../../media/18a3b451-1e64-40fc-b47f-7ce9587814bb.PNG)

Voici les topologies pris en charge. Notez la clé des graphiques :

- Si l’icône est estommée ou grisée, elle n’est pas utilisée dans le scénario.

- EXO est Exchange Online.

- SFBO est Skype Entreprise Online.

- EXCH est Exchange local.

- SFB est Skype Entreprise local.

- Les serveurs d’autorisation sont représentés par des triangles, par exemple, le Azure AD est un triangle avec un nuage derrière lui.

- Les flèches pointent vers le serveur d’autorisation qui sera utilisé lorsque les clients essaieront d’atteindre la ressource serveur spécifiée.

Tout d’abord, nous allons couvrir MA avec Skype Entreprise dans les topologies en local uniquement ou en nuage uniquement.

> [!IMPORTANT]
> Êtes-vous prêt à configurer l’authentification moderne dans Skype Entreprise Online ? Les étapes permettant d’activer cette fonctionnalité sont [ici.](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)

|Nom de la topologie  <br/> |Exemple  <br/> |Description  <br/> |Pris en charge  <br/> |
|:-----|:-----|:-----|:-----|
|Cloud uniquement  <br/> |![Prise en charge de SFB avec topologie MA, cloud uniquement.](../../media/4d19b47f-8257-4a6f-9dab-0755206f7c52.PNG)Utilisateurs d’accueil/boîtes aux lettres situées : En ligne  <br/> |MA est en place pour EXO et SFBO.  <br/> Par conséquent, le serveur d’autorisation est Azure AD.  <br/> |Authentification multifacteur (MFA), authentification basée sur le certificat client (CBA), accès conditionnel (CA)/Gestion des applications mobiles (MAM) avec Intune. \*  <br/> |
|Sur place uniquement  <br/> |![Prise en charge de SFB avec topologie MA, en local uniquement.](../../media/9773e9a5-7cd6-41ef-940b-c4386c9fce20.PNG)Utilisateurs homed/mailboxes located: On-premises  <br/> |MA est en cours pour SFB en local.  <br/> Par conséquent, le serveur d’autorisation est ADFS.  <br/> Pour plus d’informations sur la configuration, consultez [cet article.](/microsoft-365/enterprise/hybrid-modern-auth-overview) <br/> |MFA (Windows Bureau uniquement - les clients mobiles ne sont pas pris en charge). Aucune fonctionnalité Exchange’intégration.  <br/><p> **Cette approche n’est pas recommandée. Consultez les informations ci-après :** [https://aka.ms/ModernAuthOverview](/microsoft-365/enterprise/hybrid-modern-auth-overview)<p/> |

> [!IMPORTANT]
> Il est recommandé que l’état ma soit le même dans Skype Entreprise et Exchange (et leurs équivalents en ligne) pour réduire le nombre d’invites.

Les topologies mixtes impliquent des combinaisons d’hybrides de domaine partagé SFB. Voici les topologies mixtes actuellement pris en charge :

|Nom de la topologie  <br/> |Exemple  <br/> |Description  <br/> |Pris en charge  <br/> |
|:-----|:-----|:-----|:-----|
|Mixte 1  <br/> |![Prise en charge de SFB avec topologie MA, Mixte 1 (EXO + SFB).](../../media/7b2e607a-c83a-4bb3-9b48-a43566516129.PNG)           <br/> Utilisateurs d’accueil/boîtes aux lettres situées : EXO et SFB  <br/> |Ma n’est pas activée pour SFB ; aucune fonctionnalité MA SFB disponible dans cette topologie.  <br/> |Aucune fonctionnalité MA pour SFB.  <br/> |
|Mixte 2  <br/> |![Prise en charge de MA avec la topologie mixte S4B 2, SFBO et MA travaillant avec EXCH sur site.](../../media/247a985d-39cd-4c16-a19e-b8b65207d82e.PNG)           <br/> Utilisateurs homed/mailboxes located: EXCH and SFBO  <br/> |MA est uniquement sur SFBO. Le serveur d’autorisation est Azure AD pour les utilisateurs dos à dos SFBO, mais AD pour EXCH en local.  <br/> |MFA, CBA, CA/MAM avec Intune.\*  <br/> |
|Mixte 3  <br/> |![Prise en charge de MA avec SFB, EXO avec MA on, ainsi que EXCH et SFB sur site.](../../media/772dc261-c041-4a96-90d0-fd0b5124decf.PNG)           <br/> Utilisateurs d’accueil/boîtes aux lettres situées : EXO + SFB ou EXCH + SFB  <br/> |Aucune fonctionnalité MA SFB disponible dans cette topologie  <br/> |Aucune fonctionnalité MA pour SFB.  <br/> |
|Mixte 4  <br/> |![Prise en charge de MA avec SFB, SFBO avec MA on, plus EXCH et SFB.](../../media/8971bfaf-961f-476c-b16e-5418d1fa0a6d.PNG)           <br/> Utilisateurs homed/mailboxes located: EXCH +SFBO or EXCH + SFB  <br/> |MA est sur pour SFBO. Par conséquent, le serveur d’autorisation est Azure AD pour les utilisateurs doms dans SFBO. Les utilisateurs sur site dans SFB et EXO utilisent AD.  <br/> |MFA, CBA, CA/MAM avec Intune pour les utilisateurs en ligne uniquement.\*  <br/> |
|Mixte 5  <br/> |![Prise en charge de MA dans SFB, EXO avec MA et SFBO avec MA et EXCH et SFB sur site.](../../media/ecc366cf-1a7b-4ad1-bf8e-57111b8ad94f.PNG)           <br/> Utilisateurs d’accueil/boîtes aux lettres situées : EXO + SFBO, EXO + SFB, EXCH + SFBO ou EXCH + SFB  <br/> |MA est à la fois sur EXO et SFBO. Par conséquent, le serveur d’autorisation est Azure AD pour les utilisateurs dompés dans SFBO ; Les utilisateurs sur site dans EXCH et SFB utilisent AD.  <br/> |MFA, CBA, CA/MAM avec Intune pour les utilisateurs en ligne uniquement.\*  <br/> |
|Mixte 6  <br/> |![Dans une topologie mixte 6, l’authentification moderne est sur les quatre emplacements possibile , l’idéal en matière d’authentification moderne.](../../media/8de21756-9152-466d-a706-58b258e2271c.png)           <br/> Utilisateurs d’accueil/boîtes aux lettres situées : EXO + SFBO, EXO + SFB, EXCH + SFBO ou EXCH + SFB  <br/> |Ma est sur n’importe où, par conséquent le serveur d’autorisation est Azure AD pour tous les utilisateurs. (en ligne et en local)  <br/>  Veuillez consulter les [https://aka.ms/ModernAuthOverview](/microsoft-365/enterprise/hybrid-modern-auth-overview) étapes de déploiement. <br/> |MFA, CBA et CA/MAM (via Intune) pour tous les utilisateurs.  <br/> |

\*- L’mf inclut Windows ordinateurs de bureau, MAC, iOS, android et Windows mobiles ; L’ba inclut Windows ordinateurs de bureau, iOS et Android ; CA/MAM avec Intune, inclut les appareils Android et iOS.

> [!IMPORTANT]
> Il est très important de noter que les utilisateurs peuvent voir plusieurs **invites** dans certains cas, notamment lorsque l’état de l’ma n’est pas le même sur toutes les ressources serveur dont les clients peuvent avoir besoin et demander, comme c’est le cas pour toutes les versions des topologies mixtes.

> [!IMPORTANT]
> Notez également que dans certains cas (mixte 1, 3 et 5 spécifiquement), une clé de Registre [AllowADALForNonLyncIndependentOfLync](https://support.microsoft.com/help/3082803/info-about-the-allowadalfornonlyncindependentoflync-setting-in-skype-for-business,-lync-2013,-and-exchange-online) doit être définie pour une configuration appropriée pour les clients de bureau Windows.