---
title: Planification de la désactivation interne et externe des méthodes d’authentification héritées sur votre réseau
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
ms.assetid: ''
description: Cet article décrit les cmdlets qui donnent aux administrateurs plus de contrôle sur les méthodes d’authentification utilisées à l’intérieur et à l’extérieur d’une entreprise. Les administrateurs peuvent activer ou désactiver les méthodes d’authentification en interne ou en externe sur leur réseau.
ms.openlocfilehash: e2f9a8c9c8576c07de3158fb2446cb3cb89bac72
ms.sourcegitcommit: aae3eeb4dedd825ab176abe7e1aff9463c88799b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/18/2020
ms.locfileid: "46797452"
---
# <a name="planning-to-turn-off-legacy-authentication-methods-internally-and-externally-to-your-network"></a>Planification de la désactivation interne et externe des méthodes d’authentification héritées sur votre réseau.

> [!NOTE]
> Si vous êtes sur le point de lire cet article, vous devez déjà connaître les topologies d’authentification moderne prises en charge, ADAL et à propos de la configuration de l’authentification moderne, mais dans le cas contraire, Voici les articles que vous devez commencer : 
>  + [https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)
>  + [https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal](https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal)
  
L’authentification moderne ne permet pas simplement d’activer des méthodes d’authentification plus sécurisées, comme l’authentification à deux facteurs ou l’authentification basée sur les certificats, elle peut effectuer l’autorisation de votre utilisateur sans avoir besoin d’un nom d’utilisateur ou d’un mot de passe. C’est très pratique.

Cet article vous aidera à connecter des trous qui ont été exploités pour des attaques par déni de service (DOS) sur les serveurs Skype entreprise, en désactivant les méthodes plus anciennes utilisées pour l’authentification, de manière externe, en interne ou les deux, sur votre réseau. Par exemple, une meilleure méthode pour vous aider à arrêter les attaques par déni est de désactiver l’authentification Windows intégrée (qui inclut NTLM et Kerberos). La désactivation de l’authentification NTLM en externe et de l’authentification basée sur les certificats aide à protéger les mots de passe contre toute exposition. En effet, NTLM utilise les informations d’identification de mot de passe pour authentifier les utilisateurs, mais l’authentification basée sur les certificats est activée par l’authentification moderne--non. Cela signifie qu’une option idéale pour réduire les attaques DOS consiste à bloquer NTLM en externe et à n’utiliser qu’une authentification basée sur les certificats à la place.

Tout est correct, nous allons commencer.

## <a name="what-would-you-be-changing"></a>Que devez-vous modifier ? 

Ces applets de commande fonctionnent pour les points d’accès des services SIP et Web. Bien que ces deux canaux utilisent des méthodes d’accès différentes, l’exécution de la gamme de NTLM et de Kerberos à l’accès anonyme, toutes les méthodes standard utilisées par Skype entreprise ont été prises en considération.

## <a name="how-to-get-the-get--and-set-csauthconfig-cmdlets"></a>Comment obtenir les cmdlets Get-et Set-CsAuthConfig

Ces applets de commande ne seront installées qu’après la mise à jour cumulative de juillet 2018 (6.0.9319.534) pour Microsoft Skype entreprise Server 2015, et vous disposez d’une variété de topologies qui peuvent être déployées pour votre serveur Skype entreprise.

## <a name="topologies"></a>Topologies

Il est important de garder à l’esprit qu’il s’agit des topologies prises en charge dans ce scénario. Si vous devez accéder à la prise en charge de l’aide pour bloquer une méthode, par exemple, vous devrez disposer d’une configuration parmi les types ci-dessous. 

> [!IMPORTANT]
> Dans le tableau et les descriptions ci-dessous, *l’authentification moderne* est abrégée en __ma__ et *l’authentification intégrée de Windows* est abrégée en __Win__. En guise de rappel, l’authentification intégrée de Windows est composée de deux méthodes : NTLM et authentification Kerberos. Vous devez en savoir plus pour lire le tableau correctement !


|       |En externe  |En interne  |Paramètre  |
|---------|:---------|:---------|---------|
|__Type 1__   |  MA + Win       | MA + Win         |  AllowAllExternallyAndInternally       |
|__Type 2__   |  MA       | MA + Win         | BlockWindowsAuthExternally        |
|__Type 3__   |  MA       | MA        | BlockWindowsAuthExternallyAndInternally        |
|__Type 4__   |  MA       | Conclure        | BlockWindowsAuthExternallyAndModernAuthInternally    |
|__Type 5__   |  MA + Win       | Conclure        | BlockModernAuthInternally         |

__Type 1 Description :__ Il s’agit du scénario par défaut lorsque MA est __activée pour Skype__ entreprise Server. En d’autres termes, il s’agit du *point de départ* lorsque ma est configurée.

__Tapez 2 Description :__ Cette topologie bloque NTLM en *externe*, mais autorise NTLM ou Kerberos (pour les clients qui ne prennent pas en charge Adal) à fonctionner en *interne*. Si vos clients prennent en charge ADAL, ils utiliseront l’agent de-prise en charge en interne.

__Tapez 3 Description :__ Cette topologie requiert l’agent de démarrage pour tous les utilisateurs. Tous vos clients compatibles ADAL fonctionneront dans cette topologie, et les mots de passe ne seront pas exploités si, par exemple, vous désactivez l’utilisation de mots de passe avec l’authentification par certificat.

__Tapez 4 Description :__ Cette topologie bloque NTLM de manière interne et *externe* . Il permet à *tous les clients* d’utiliser les méthodes d’authentification héritées en *interne* (même les clients compatibles avec Adal).

__Type 5 Description :__ en *externe*, vos clients Adal modernes utiliseront l’agent de réception et tous les clients qui ne prennent pas en charge Adal utiliseront des méthodes d’authentification héritées. Mais, en *interne* , *tous les clients* utiliseront l’authentification héritée (y compris tous les clients compatibles avec Adal).

Il est assez facile de savoir comment protéger vos mots de passe dans les options disponibles. N’oubliez pas que la situation idéale consiste à utiliser l’agent de configuration externe (par exemple, en configurant l’authentification par certificat) afin d’éviter les attaques par déni de compte. Si vous l’utilisez en interne pour vos clients modernes, vous devrez également vérifier votre réseau à l’avenir concernant les attaques de Skype entreprise Server.

## <a name="why-to-use-set-csauthconfig-at-the-global-level"></a>Pourquoi utiliser SET-CsAuthConfig au niveau global ?

La `Set-CsAuthConfig` Configuration des effets des applets de commande sur les rôles serveur d’inscriptions et services Web.

Cette applet de commande est conçue pour être exécutée au niveau global de votre serveur Skype entreprise. Elle *peut* être exécutée au niveau du pool, mais cela n’est *pas recommandé* , car elle ajoute de la complexité à votre installation. En exécutant ces commandes au niveau du pool, si votre pool ne dispose pas de tous les rôles inclus (par exemple, s’il n’a pas de services Web), les paramètres ne seront définis que pour le rôle de serveur d’inscriptions. Dans ce cas, les services Web s’exécuteront avec des paramètres du niveau global, qui peuvent être un comportement confus (en particulier lorsque cela est fait par inadvertance).

Si un client utilise les paramètres du serveur d’inscriptions d’un pool et les paramètres des services Web d’un autre pool et que les paramètres d’authentification sont dans un état incohérent, les clients yous peuvent ne pas être en mesure de se connecter.

En outre, s’il n’existe qu’un seul rôle pour un pool : 
* Set-définit uniquement les paramètres qui correspondent au rôle existant. Aucun avertissement particulier n’est fourni, car certains paramètres n’ont *pas* été définis. 
* Get-renverra le paramètre qui correspond au rôle existant, et les paramètres globaux pour le rôle qui n’existe pas.
* Si aucun rôle n’est présent pour un pool, Set-et Get-renvoient un message d’erreur.
* Si les deux rôles sont présents pour un pool mais que les stratégies ne sont pas définies au niveau du pool, Get-renvoie un message d’erreur.

Il peut s’avérer plus judicieux d’effectuer une opération Get-pour ces valeurs, et de faire une capture d’écran ou d’enregistrer leur état de départ avant d’apporter des modifications. Vous pouvez également envisager de conserver un journal des modifications apportées dans un OneNote.

> [!NOTE]
> 
> Remarque : après avoir configuré l’CsAuthConfig, vous devez exécuter Enable-CsComputer sur chaque ordinateur afin que les paramètres prennent effet.

> [!IMPORTANT]
> Si vous utilisez l’utilisation de Lync Web Access (LWA) et que vous devez utiliser l’accès basé sur les formulaires (FBA) pour l’accès externe, reconfigurez LWA afin que les clients puissent y accéder avec un accès anonyme pour prendre en charge ces scénarios. De même, si vous utilisez le code confidentiel d’accès, le FBA est bloqué uniquement pour les utilisateurs externes. S’ils ont besoin de modifier leur code confidentiel, ils devront se connecter à leur entreprise en interne.

> [!NOTE]
> 
> Si vous utilisez le paramètre BlockWindowsAuthExternally pour bloquer l’authentification NTLM de manière externe, sachez que cela bloque également NTLM en interne pour le canal SIP. Toutefois, les clients Skype entreprise et Lync plus récents que 2010 pourront toujours se connecter car ils utiliseront NTLM sur HTTP pour la connexion, en interne, puis extrayez un certificat pour se connecter via SIP. Toutefois, les clients antérieurs à 2010 ne pourront pas se connecter en interne dans ce cas, et vous pouvez envisager de mettre à niveau ces applications afin que les utilisateurs puissent reprendre leur fonctionnalité sécurisée.

> [!IMPORTANT] 
> Certaines applications Web Skype entreprise ne prennent pas en charge l’agent de gestion. À l’aide du scénario BlockWindowsAuthExternallyAndInternally, vous ne pourrez pas accéder à ces applications. Les applications sans prise en charge de l’agent de gestion de la page sont Web Scheduler, page Dial-in, Skype entreprise Control Panel (CSCP) et Response Group Group Settings. 

## <a name="links"></a>Links 
- Pour plus d’informations sur PowerShell :
    -  [Get-CsAuthConfig](https://docs.microsoft.com/powershell/module/skype/get-csauthconfig?view=skype-ps)
    -  [Set-CsAuthConfig](https://docs.microsoft.com/powershell/module/skype/set-csauthconfig?view=skype-ps)

- Pour plus d’informations sur l’utilisation des commandes ou de la mise à jour cumulative pour les installer :
    - [Briefing des applets de commande](https://support.microsoft.com/help/4346673/new-cmdlets-to-manage-skype-for-business-server-2015-authentication)
    - [Mises à jour de Skype entreprise Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015) (général)
    - Le 6.0.9319.534 [de juillet 2018 Skype entreprise Server 2015, composants principaux cu](https://support.microsoft.com/help/4340903/july-2018-cumulative-update-6-0-9319-534-for-skype-for-business-server) ()


 
