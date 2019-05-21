---
title: Planification de la désactivation de méthodes d’authentification héritées internes et externes à votre réseau
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: tracyp
ms.assetid: ''
description: Cet article présente des applets de commande qui fournissent aux administrateurs davantage de contrôle sur les méthodes d’authentification utilisées à l’intérieur et à l’extérieur d’une entreprise. Les administrateurs peuvent activer ou désactiver les méthodes d’authentification en interne, ou en externe sur leur réseau.
ms.openlocfilehash: aaee46b04832cc114f895f905c180fe089d7349d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297266"
---
# <a name="planning-to-turn-off-legacy-authentication-methods-internally-and-externally-to-your-network"></a>Planification de la désactivation de méthodes d’authentification héritées internes et externes à votre réseau.

> [!NOTE]
> Si vous êtes sur le point de lire cet article, vous devez en savoir plus sur les topologies d’authentification modernes prises en charge, les ADAL et la configuration de l’authentification moderne, mais si ce n’est pas le cas, Voici les articles dont vous avez besoin pour commencer: 
>  + [https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)
>  + [https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal](https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal)
  
L’authentification moderne n’autorise pas seulement les méthodes d’authentification plus sécurisées, telles que l’authentification à deux facteurs ou l’authentification par certificat, elle peut également faire l’autorisation de l’utilisateur sans avoir besoin d’un nom d’utilisateur ou d’un mot de passe. C’est très pratique.

Cet article vous aide à brancher des trous qui ont été exploités pour les attaques de déni de service (DOS) sur les serveurs Skype entreprise, en désactivant les méthodes plus anciennes utilisées pour l’authentification, l’extérieur, en interne, ou les deux, à votre réseau. Par exemple, il est conseillé de désactiver l’authentification intégrée Windows (qui inclut NTLM et Kerberos) pour empêcher les attaques par déni de compte. La désactivation de NTLM en externe et l’authentification par certificat vous aide à protéger les mots de passe de l’exposition. En effet, NTLM utilise les informations d’identification d’un mot de passe pour authentifier les utilisateurs, mais ce n’est pas le cas pour l’authentification basée sur le certificat. En d’autres termes, une option idéale pour réduire les attaques par déni de fonction consiste à bloquer l’utilisation de NTLM en externe et à plutôt utiliser cette méthode d’authentification basée sur les certificats.

C’est parti!

## <a name="what-would-you-be-changing"></a>Que voulez-vous changer? 

Ces applets de action fonctionnent pour les points d’accès SIP et Web services. Bien que ces deux canaux utilisent des méthodes d’accès différentes, qui exécutent la gamme de protocoles NTLM et Kerberos en accès anonyme, toutes les méthodes standard utilisées par Skype entreprise sont prises en compte.

## <a name="how-to-get-the-get--and-set-csauthconfig-cmdlets"></a>Comment obtenir les applets de applet Get et Set-CsAuthConfig

Ces applets de applet ne seront installés qu’après la mise à jour cumulative de juillet 2018 (6.0.9319.534) pour Microsoft Skype entreprise Server 2015, et vous disposez de diverses topologies qui peuvent être déployées pour votre serveur Skype entreprise.

## <a name="topologies"></a>Topologies

Il est important de garder à l’esprit que ces topologies sont prises en charge dans ce scénario. Si vous avez besoin d’aide pour bloquer une méthode, par exemple, vous devrez disposer d’une configuration parmi les types ci-dessous. 

> [!IMPORTANT]
> Dans la table et les descriptions ci-dessous, l' *authentification moderne* est abrégée en __ma__ et *l’authentification intégrée de Windows* est abrégée par __Win__. Pour rappel, l’authentification intégrée de Windows est composée de deux méthodes: authentification NTLM et Kerberos. Vous devez en savoir plus pour lire correctement le tableau.


|       |En externe  |En interne  |Paramètre  |
|---------|:---------|:---------|---------|
|__Taper 1__   |  MA + Win       | MA + Win         |  AllowAllExternallyAndInternally       |
|__Tapez 2__   |  TÉLÉPHONIQUE       | MA + Win         | BlockWindowsAuthExternally        |
|__Tapez 3__   |  TÉLÉPHONIQUE       | TÉLÉPHONIQUE        | BlockWindowsAuthExternallyAndInternally        |
|__Taper 4__   |  TÉLÉPHONIQUE       | Êtes        | BlockWindowsAuthExternallyAndModernAuthInternally    |
|__Tapez 5__   |  MA + Win       | Êtes        | BlockModernAuthInternally         |

__Tapez 1 Description:__ Il s’agit du scénario par défaut lorsque MA ____ société est activée pour Skype entreprise Server. En d’autres termes, il s’agit du *point de départ* lorsque ma est configuré.

__Tapez 2 Description:__ Cette topologie bloque NTLM de manière *externe*, mais autorise NTLM ou Kerberos (pour les clients qui ne prennent pas en charge Adal) pour fonctionner en *interne*. Si vos clients prennent en charge ADAL, ils utiliseront le MA en interne.

__Tapez 3 Description:__ Cette topologie nécessite le MA pour tous les utilisateurs. Tous vos clients compatibles ADAL fonctionneront dans cette topologie, et les mots de passe ne seront pas utilisés si, par exemple, vous désactivez l’utilisation des mots de passe avec l’authentification par certificat.

__Tapez 4 Description:__ Cette topologie bloque NTLM en *externe* et ma topologie en interne. Il permet à *tous les clients* d’utiliser les méthodes d’authentification héritées en *interne* (même les clients compatibles avec Adal).

__Tapez 5 Description:__ En *externe*, vos clients Adal modernes utilisent ma et les clients qui ne prennent pas en charge Adal utiliseront les méthodes d’authentification héritées. Toutefois, ** *tous les clients* utilisent en interne l’authentification héritée (y compris tous les clients compatibles Adal).

C’est très facile de savoir comment protéger vos mots de passe dans les options disponibles. Gardez à l’esprit que la situation idéale consiste à utiliser l’extérieur de manière externe (par exemple, en configurant l’authentification par certificat) pour éviter les attaques par déni de compte. Si vous utilisez l’application en interne pour vos clients modernes, vous devez également vérifier votre réseau en ce qui concerne les attaques par déni de service de Skype entreprise Server.

## <a name="why-to-use-set-csauthconfig-at-the-global-level"></a>Pourquoi utiliser SET-CsAuthConfig au niveau global

La `Set-CsAuthConfig` configuration des effets d’applet de passe sur les rôles Bureau d’enregistrement et services Web.

Ce cmdlet est censé être exécuté au niveau global de votre serveur Skype entreprise. Il *peut* être exécuté au niveau du pool, mais cela n’est *pas recommandé* , car il ajoute de la complexité à votre installation. En exécutant ces commandes au niveau du pool, si vous n’avez pas ajouté tous les rôles (par exemple, si la liste ne comporte pas de services Web), les paramètres ne sont définis que pour le rôle Bureau d’enregistrement. Dans ce cas, les services Web utiliseront des paramètres du niveau global, ce qui peut être un comportement confus (en particulier, lorsque cela est réalisé involontairement).

Si un client utilise les paramètres du Bureau d’enregistrement d’un pool et les paramètres de services Web d’un autre pool et les paramètres d’authentification sont dans un état incohérent, il est possible que les clients yous ne puissent pas se connecter.

Par ailleurs, s’il n’y a qu’un seul rôle pour une liste: 
* Set-définira uniquement les paramètres correspondant au rôle existant. Aucun avertissement spécial n’est accordé car certains paramètres n’ont *pas* été définis. 
* Get-renverra le paramètre correspondant au rôle existant et les paramètres globaux pour le rôle qui n’existe pas.
* Si aucun de ses rôles n’est présent pour un pool, la fonction Set et Get-renverra un message d’erreur.
* Si les deux rôles sont présents pour un pool mais que les stratégies ne sont pas définies au niveau du pool, Get-renverra un message d’erreur.

Il est recommandé d’effectuer une opération Get pour obtenir ces valeurs et d’effectuer une capture d’écran ou d’enregistrer leur état de départ avant d’apporter des modifications. Vous pouvez également envisager de consigner les modifications dans OneNote.

> [!NOTE]
> 
> Remarque: après avoir configuré le CsAuthConfig, vous devez exécuter Enable-CsComputer sur chaque ordinateur pour que les paramètres soient pris en compte.

> [!IMPORTANT]
> Si vous utilisez Lync Web Access (LWA) et devez utiliser l’accès basée sur les formulaires (FBA) pour l’accès externe, reconfigurez LWA de sorte que les clients puissent y accéder avec l’accès anonyme pour prendre en charge ces scénarios. De même, si vous utilisez un code confidentiel de conférence rendez-vous, le FBA est bloqué uniquement pour les utilisateurs externes. S’il a besoin de modifier son code confidentiel, il doit se connecter à son entreprise pour le faire en interne.

## <a name="links"></a>Liens 
- Pour plus d’informations sur PowerShell:
    -  [Get-CsAuthConfig](https://docs.microsoft.com/powershell/module/skype/get-csauthconfig?view=skype-ps)
    -  [Set-CsAuthConfig](https://docs.microsoft.com/en-us/powershell/module/skype/set-csauthconfig?view=skype-ps)

- Pour plus d’informations sur l’utilisation des commandes ou sur la fonction CU requise pour les installer, procédez comme suit:
    - [Briefing des cmdlets](https://support.microsoft.com/en-us/help/4346673/new-cmdlets-to-manage-skype-for-business-server-2015-authentication)
    - [Mises à jour de Skype entreprise Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015) Feuille
    - Le [2018 de juillet, Skype entreprise Server 2015, composants principaux de Cu](https://support.microsoft.com/en-us/help/4340903/july-2018-cumulative-update-6-0-9319-534-for-skype-for-business-server) (6.0.9319.534)


 
