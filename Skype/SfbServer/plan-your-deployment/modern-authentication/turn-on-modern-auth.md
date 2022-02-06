---
title: Planification de la désactiver des méthodes d’authentification héritées en interne et en externe sur votre réseau
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.custom: tracyp
ms.assetid: null
description: Cet article décrit les cmdlets qui donnent aux administrateurs davantage de contrôle sur les méthodes d’authentification utilisées à l’intérieur et à l’extérieur d’une entreprise. Les administrateurs peuvent activer ou désactiver les méthodes d’authentification en interne ou en externe sur leur réseau.
---

# <a name="planning-to-turn-off-legacy-authentication-methods-internally-and-externally-to-your-network"></a>Planification de la désactiver des méthodes d’authentification héritées en interne et en externe sur votre réseau.

> [!NOTE]
> Si vous êtes sur le point de lire cet article, vous devez déjà connaître les topologies d’authentification moderne, ADAL et la config d’authentification moderne, mais, si ce n’est pas le cas, voici les articles que vous devez commencer : 
>  + [https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported](./topologies-supported.md)
>  + [https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal](/skypeforbusiness/manage/authentication/use-adal)
  
L’authentification moderne n’active pas seulement des méthodes d’authentification plus sécurisées, telles que l’authentification Two-Factor ou l’authentification basée sur un certificat, elle peut également effectuer l’autorisation de votre utilisateur sans avoir besoin d’un nom d’utilisateur ou d’un mot de passe. C’est très pratique.

Cet article vous aidera à brancher les trous qui ont été exploités pour les attaques par déni de service (DOS) sur les serveurs Skype Entreprise, en détourant les anciennes méthodes utilisées pour l’authentification, en externe, en interne ou les deux, sur votre réseau. Par exemple, une bonne méthode pour arrêter les attaques DOS consisterait à désactiver l’authentification Windows intégrée (qui inclut NTLM et Kerberos). La mise hors réseau de NTLM en externe et l’authentification basée sur les certificats permettent de protéger les mots de passe contre l’exposition. En effet, NTLM utilise les informations d’identification de mot de passe pour authentifier les utilisateurs, mais pas l’authentification basée sur les certificats (activée par l’authentification moderne). Cela signifie qu’une option idéale pour réduire les attaques DOS consiste à bloquer NTLM en externe et à utiliser uniquement l’authentification basée sur les certificats à cet emplacement.

Commençons.

## <a name="what-would-you-be-changing"></a>Que modifieriez-vous ? 

Ces cmdlets fonctionnent pour les points d’accès SIP et Web Services. Bien que ces deux canaux utilisent des méthodes d’accès différentes, en exécutant la gamme de NTLM et Kerberos en accès anonyme, toutes les méthodes standard utilisées par Skype Entreprise ont été prises en compte.

## <a name="how-to-get-the-get--and-set-csauthconfig-cmdlets"></a>Comment obtenir les cmdlets Get-and-Set-CsAuthConfig

Ces cmdlets seront installées uniquement après la mise à jour cumulative de juillet 2018 (6.0.9319.534) pour Microsoft Skype Entreprise Server 2015, puis vous avez plusieurs topologies qui peuvent être déployées pour votre serveur Skype Entreprise.

## <a name="topologies"></a>Topologies

Il est important de garder à l’esprit qu’il s’agit des topologies pris en charge impliquées dans ce scénario ! Si vous devez obtenir de l’aide sur le blocage d’une méthode, par exemple, vous devez avoir une configuration parmi les types ci-dessous. 

> [!IMPORTANT]
> Dans le tableau et les descriptions ci-dessous *,* l’authentification moderne est abrégée en __MA__ et *Windows l’authentification* intégrée est abrégée __win__. Pour rappel, Windows’authentification intégrée est composé de deux méthodes : l’authentification NTLM et l’authentification Kerberos. Vous devez le savoir pour lire correctement le tableau !


|       |Externe  |En interne  |Paramètre  |
|---------|:---------|:---------|---------|
|__Type 1__   |  MA + Win       | MA + Win         |  AllowAllExternallyAndInternally       |
|__Type 2__   |  MA       | MA + Win         | BlockWindowsAuthExternally        |
|__Type 3__   |  MA       | MA        | BlockWindowsAuthExternallyAndInternally        |
|__Type 4__   |  MA       | Win        | BlockWindowsAuthExternallyAndModernAuthInternally    |
|__Type 5__   |  MA + Win       | Win        | BlockModernAuthInternally         |

__Type 1 Description :__ Il s’agit du scénario par défaut lorsque MA est __Skype Entreprise Server__. En d’autres termes, il s’agit du *point de départ* lorsque MA est configuré.

__Type 2 Description :__ Cette topologie bloque *NTLM en* externe, mais permet à NTLM ou Kerberos (pour les clients qui ne supportent pas ADAL) de fonctionner *en interne*. Si vos clients ne supportent pas ADAL, ils utiliseront MA en interne.

__Type 3 Description :__ Cette topologie nécessite MA pour tous les utilisateurs. Tous vos clients ADAL fonctionneront dans cette topologie et les mots de passe ne seront pas utilisés si, par exemple, vous désactiverez l’utilisation des mots de passe avec l’th basée sur un certificat.

__Type 4 Description :__ Cette topologie bloque NTLM *en externe et* ma en interne. Il permet à tous *les clients* d’utiliser les méthodes d’authentification héritées en *interne* (même les clients ADAL).

__Type 5 Description :__ *en externe*, vos clients ADAL modernes utiliseront MA et tous les clients qui ne la prisent pas en charge utiliseront les méthodes d’authentification héritées. Toutefois, *en interne,* *tous les clients* utiliseront l’authentification héritée (y compris tous les clients ADAL).

Il est assez facile de perdre le suivi de l’objectif de protection de vos mots de passe dans les options disponibles. Gardez à l’esprit que la situation idéale est d’utiliser ma en externe (par exemple, en configurant l’th basée sur les certificats), pour éviter les attaques DOS. Si vous l’exploitez en interne pour vos clients modernes, vous prouverez également à l’avenir que votre réseau Skype Entreprise Server attaques DOS.

## <a name="why-to-use-set-csauthconfig-at-the-global-level"></a>Pourquoi utiliser Set-CsAuthConfig au niveau global ?

L’cmdlet `Set-CsAuthConfig` a une incidence sur la configuration des rôles Serveur d’inscriptions et Services Web.

Cette cmdlet est destinée à être exécuté au niveau global de votre Skype Entreprise serveur. Il *peut* être exécuté au niveau du pool, mais ce  n’est pas recommandé, car il ajoute de la complexité à votre installation. En exécutant ces commandes au niveau du pool, si tous les rôles de votre pool ne sont pas inclus (par exemple, il n’a pas de services Web), les paramètres sont uniquement définies pour le rôle Serveur d’inscriptions. Dans ce cas, les services Web s’effectuent avec les paramètres du niveau global, ce qui peut prêter à confusion (en particulier lorsque cela est effectué involontairement).

Si un client utilise les paramètres du serveur d’inscriptions d’un pool et les paramètres des services web d’un autre pool et que les paramètres d’authentification sont dans un état incohérent, les clients yous risquent de ne pas pouvoir se connecter.

En outre, s’il n’existe qu’un seul rôle pour un pool : 
* Set- ne définira que les paramètres correspondant au rôle qui existe. Aucun avertissement spécial ne sera donné, car certains paramètres n’ont *pas été définies* . 
* Get- retourne le paramètre qui correspond au rôle qui existe et les paramètres globaux pour le rôle qui n’existe pas.
* Si aucun rôle n’est présent pour un pool, Set- et Get- retournent un message d’erreur.
* Si les deux rôles sont présents pour un pool mais que les stratégies ne sont pas définies au niveau du pool, Get- retourne un message d’erreur.

Il peut être plus judicieux d’effectuer une get- pour ces valeurs et d’effectuer une capture d’écran ou d’enregistrer leur état de départ avant d’apporter des modifications. Vous pouvez également envisager de conserver un journal des modifications dans un OneNote.

> [!NOTE]
> 
> Remarque : après avoir configuré CsAuthConfig, vous devez exécuter Enable-CsComputer sur chaque ordinateur pour que les paramètres prennent effet.

> [!IMPORTANT]
> Si vous utilisez Lync Web Access (LWA) et que vous devez utiliser l’accès basé sur les formulaires pour l’accès externe, reconfigurez LWA afin que les clients y accèdent avec l’accès anonyme pour prendre en charge ces scénarios. De même, si vous utilisez le code confidentiel d’accès, l’AD FBA sera bloqué pour les utilisateurs externes uniquement. S’ils ont besoin de modifier leur code confidentiel, ils devront se connecter à leur entreprise pour le faire, en interne.

> [!NOTE]
> 
> Si vous utilisez le paramètre BlockWindowsAuthExternally pour bloquer NTLM en externe, sachez que cela bloque également NTLM en interne pour le canal SIP. Toutefois, les clients Skype Entreprise et Lync plus nouveaux que 2010 pourront toujours se connecter, car ils utiliseront NTLM sur HTTP pour se connecter, en interne, puis extraire un certificat pour se connecter sur SIP. Toutefois, les clients plus anciens que 2010 ne pourront pas se connecter en interne dans ce cas, et vous pouvez envisager de mettre à niveau ces applications afin que vos utilisateurs puissent reprendre les fonctionnalités sécurisées.

> [!IMPORTANT] 
> Certaines applications web Skype Entreprise ne sont pas en charge par ma. Ainsi, en utilisant le scénario BlockWindowsAuthExternallyAndInternally, vous ne pourrez pas accéder à ces applications. Les applications sans prise en charge de l’Skype Entreprise web sont les suivantes : Web Scheduler, Dial-In Page, Skype Entreprise Control Panel (CSCP) et Response Group Paramètres Page. 

## <a name="links"></a>Liens 
- Pour plus d’informations sur PowerShell :
    -  [Get-CsAuthConfig](/powershell/module/skype/get-csauthconfig?view=skype-ps)
    -  [Set-CsAuthConfig](/powershell/module/skype/set-csauthconfig?view=skype-ps)

- Pour plus d’informations sur l’utilisation des commandes ou sur la mise à jour cu nécessaire pour les installer :
    - [Briefing sur les cmdlets](https://support.microsoft.com/help/4346673/new-cmdlets-to-manage-skype-for-business-server-2015-authentication)
    - [Mises à jour Skype Entreprise Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015) (général)
    - La [cu des composants principaux de juillet 2018 Skype Entreprise Server 2015](https://support.microsoft.com/help/4340903/july-2018-cumulative-update-6-0-9319-534-for-skype-for-business-server) (6.0.9319.534)


