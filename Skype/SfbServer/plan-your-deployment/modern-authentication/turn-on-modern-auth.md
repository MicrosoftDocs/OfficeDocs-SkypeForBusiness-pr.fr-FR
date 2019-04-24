---
title: Planification de désactiver les méthodes d’authentification Legacy internes et externes à votre réseau
ms.reviewer: ''
ms.author: tracyp
author: MSFTTracyP
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: tracyp
ms.assetid: ''
description: Cet article plans les applets de commande qui offrent des administrateurs plus de contrôle des méthodes d’authentification utilisée à l’intérieur et en dehors d’une entreprise. Les administrateurs peuvent activer des méthodes d’authentification soit désactivée en interne ou externe à leur réseau.
ms.openlocfilehash: 08f8b850fbde99f85f804494eab79a9a3531d009
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213899"
---
# <a name="planning-to-turn-off-legacy-authentication-methods-internally-and-externally-to-your-network"></a>Envisagez de désactiver les méthodes d’authentification Legacy internes et externes à votre réseau.

> [!NOTE]
> Si vous êtes sur le point de lire cet article, vous devez déjà connaître à propos des topologies d’authentification moderne pris en charge, ADAL, et sur la configuration de l’authentification moderne, mais, au cas où vous n’avez pas, voici les articles que vous avez besoin pour commencer : 
>  + [https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)
>  + [https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal](https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal)
  
Authentification moderne n’activer simplement le plus sécurisés méthodes d’authentification, telles que l’authentification à deux facteurs ou authentification basée sur les certificats, il peut exécuter l’autorisation de l’utilisateur sans avoir besoin d’un nom d’utilisateur ou le mot de passe trop. Il est très pratique.

Cet article vous permettra de trous plug qui ont été exploitées pour les attaques par déni de Service (DOS) sur Skype pour des serveurs d’entreprise, en désactivant les anciennes méthodes utilisées pour l’authentification, en externe, en interne, ou les deux, à votre réseau. Par exemple, une bonne méthode pour empêcher les attaques par déni de service serait pour désactiver l’authentification intégrée Windows (qui inclut NTLM et Kerberos). Désactivation de NTLM en externe et dépend de l’authentification par certificat permettent de protéger les mots de passe de l’exposition. Il s’agit, car NTLM utilise les informations d’identification de mot de passe pour authentifier les utilisateurs, mais ne pas de certificat d’authentification--activée par Auth moderne--. Que signifie une solution idéale pour réduire les attaques de déni de service consiste à bloquer NTLM en externe et utiliser uniquement l’authentification avec certificat, au lieu de cela.

Tous les droits, nous allons commencer.

## <a name="what-would-you-be-changing"></a>Ce qui souhaiteriez vous modifier ? 

Ces applets de commande fonctionnent pour SIP et des Services Web des points d’accès. Même si ces deux canaux utiliser les méthodes d’accès différentes, allant de la gamme NTLM et Kerberos pour l’accès anonyme, toutes les méthodes standards utilisés par Skype pour les entreprises ont été prises en considération.

## <a name="how-to-get-the-get--and-set-csauthconfig-cmdlets"></a>Comment obtenir les applets de commande Get - et Set-CsAuthConfig

Ces applets de commande ne sera installés publier juillet 2018 mise à jour cumulative (6.0.9319.534) pour Microsoft Skype pour Business Server 2015, et vous avez une variété de topologies pouvant être déployés pour votre Skype pour Business server.

## <a name="topologies"></a>Topologies

Il est important de garder à l’esprit qu’il s’agit les Topologies prises en charge impliquée dans ce scénario. Si vous avez besoin accéder à la prise en charge pour vous aider à bloquer une méthode, par exemple, vous devrez disposent d’une configuration entre les types ci-dessous. 

> [!IMPORTANT]
> Dans la table et les descriptions ci-dessous, __MA__ abréviation est utilisée pour *L’authentification moderne* et *L’authentification Windows intégrée* est abrégé en tant que __Win__. Pour rappel, l’authentification Windows intégrée est composée de deux méthodes : l’authentification NTLM et Kerberos. Vous devez connaître pour lire la table correctement !


|       |En externe  |En interne  |Paramètre  |
|---------|:---------|:---------|---------|
|__Type 1__   |  MA + Win       | MA + Win         |  AllowAllExternallyAndInternally       |
|__Type 2__   |  AGENT DE GESTION       | MA + Win         | BlockWindowsAuthExternally        |
|__Type 3__   |  AGENT DE GESTION       | AGENT DE GESTION        | BlockWindowsAuthExternallyAndInternally        |
|__Type 4__   |  AGENT DE GESTION       | Win        | BlockWindowsAuthExternallyAndModernAuthInternally    |
|__Type 5__   |  MA + Win       | Win        | BlockModernAuthInternally         |

__Tapez 1 Description :__ Il s’agit de la valeur par défaut __scénario lorsque MA est activé pour Skype pour Business Server__ . En d’autres termes, il s’agit du *point de départ* lorsque MA est configurée.

__Description du type 2 :__ Cette topologie bloque NTLM *en externe*, tout en autorisant NTLM ou Kerberos (pour les clients qui ne prennent pas en charge ADAL) fonctionne *en interne*. Si vos clients ne prennent pas en charge ADAL ils utiliseront MA en interne.

__Description du type 3 :__ Cette topologie nécessite un agent de gestion pour tous les utilisateurs. Tous les clients compatibles ADAL fonctionneront dans cette topologie, et les mots de passe ne seront pas exploitées si, par exemple, vous désactivez l’utilisation de mots de passe avec l’authentification basée sur certificat

__Description du type 4 :__ Cette topologie bloque NTLM *en externe* et MA en interne. Il permet à *tous les clients* à utiliser l’authentification hérité méthodes *en interne* (même compatibles ADAL clients).

__Description du type 5 :__ *En externe*, vos clients ADAL modernes utiliseront MA et les clients qui ne prennent pas en charge ADAL utilisera des méthodes d’authentification hérité. Mais, *en interne* *tous les clients* utiliseront l’authentification héritée (y compris tous les clients compatibles ADAL).

Il est facile de perdre la trace de l’objectif de la protection de votre mot de passe dans les options disponibles. N’oubliez pas l’idéal consiste à utiliser MA en externe (par exemple, en configuration basée sur certificat auth), pour éviter les attaques par déni de service. Si vous en faites en interne pour vos clients modernes, vous aurez également durable votre réseau concernant Skype pour les attaques de déni de service Business Server.

## <a name="why-to-use-set-csauthconfig-at-the-global-level"></a>Pourquoi utiliser Set-CsAuthConfig au niveau Global

Le `Set-CsAuthConfig` cmdlet effets configuration sur le serveur d’inscriptions et les rôles de Services Web.

Cette applet de commande est destinée à être exécutée au niveau Global de votre Skype pour Business server. Il *peut* être exécuté sur le niveau du Pool, mais qui est *pas recommandé* car la complexité est ajouté à votre installation. En exécutant les commandes suivantes au niveau du Pool, si votre Pool ne possède pas tous les rôles inclus (par exemple, il ne possède pas les Services Web), les paramètres n’est définies pour le rôle de serveur d’inscriptions. Dans ce cas, les Services Web seront poursuivre avec les paramètres de niveau Global, qui peut être difficile de comportement (en particulier lorsque cette opération est effectuée par inadvertance).

Si un client utilise les paramètres du serveur d’inscriptions d’un pool et les paramètres des Services Web à partir d’un autre pool et les paramètres d’authentification sont dans un état instable, yous clients peuvent être impossible de se connecter.

En outre, s’il n'existe qu’un seul rôle pour un pool : 
* Set-vont définie uniquement les paramètres qui correspondent au rôle qui existe. Aucun avertissement spéciaux ne recevront car certains paramètres n’est *pas* la valeur. 
* Get-sera retourne le paramètre qui correspond au rôle qui existe et les paramètres globaux pour le rôle qui n’existe pas.
* Si aucun rôle n’est présent pour un pool, les deux seront Set et Get retourne un message d’erreur.
* Si les deux rôles sont présents pour un pool, mais les stratégies ne sont pas définis au niveau du pool, Get-sera retourne un message d’erreur.

Il peut être préférable d’effectuer un Get-pour ces valeurs et pour la capture d’écran ou d’enregistrer leur état initial avant d’apporter des modifications. Vous pouvez également envisager de conserver un journal des modifications apportées dans un OneNote.

> [!NOTE]
> 
> Remarque : Après avoir configuré le CsAuthConfig, vous devez exécuter Enable-CsComputer sur chaque ordinateur pour que les paramètres prennent effet.

> [!IMPORTANT]
> Si vous utilisez Lync Web Access (LWA) et que vous devez utiliser Access basée sur les formulaires (FBA) pour l’accès externe, reconfigurez LWA afin que les clients puissent y accéder avec un accès anonyme pour prendre en charge ces scénarios. De même, si vous utilisez le code d’appel confidentiel, FBA est bloquée pour les utilisateurs externes. S’ils ont besoin de modifier leur code confidentiel, ils seront doivent se connecter à leur entreprise à le faire en interne.

## <a name="links"></a>Liens 
- Pour plus d’informations PowerShell :
    -  [Get-CsAuthConfig](https://docs.microsoft.com/powershell/module/skype/get-csauthconfig?view=skype-ps)
    -  [Set-CsAuthConfig](https://docs.microsoft.com/en-us/powershell/module/skype/set-csauthconfig?view=skype-ps)

- Pour plus d’instructions sur la façon d’utiliser les commandes ou sur la mise à jour Cumulative nécessaires pour les installer :
    - [Applets de commande exécutif](https://support.microsoft.com/en-us/help/4346673/new-cmdlets-to-manage-skype-for-business-server-2015-authentication)
    - [Mises à jour pour Skype pour Business Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015) (Général)
    - Le [juillet 2018 Skype pour Business Server 2015, mise à jour Cumulative des composants de base](https://support.microsoft.com/en-us/help/4340903/july-2018-cumulative-update-6-0-9319-534-for-skype-for-business-server) (6.0.9319.534)


 
