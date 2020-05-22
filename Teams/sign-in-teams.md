---
title: Se connecter à Teams en utilisant l’authentification moderne
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: Découvrez comment fonctionne l’authentification moderne, comment changer de compte et comment résoudre les problèmes liés à l’authentification moderne. Inclut comment demander à Teams d'ignorer le pré-remplissage du nom de l'utilisateur (UPN) à l’ouverture de session.
ms.custom: seo-marvel-apr2020
localization_priority: Priority
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 63bfd0cb9fe4292b180dfc6a0c7852b3c90a8bc4
ms.sourcegitcommit: 624bd511b96cf213483d3ea8f27b20a91d955550
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2020
ms.locfileid: "44330539"
---
<a name="sign-in-to-microsoft-teams-using-modern-authentication"></a>Se connecter à Microsoft Teams en utilisant l’authentification moderne
==========================

Microsoft recommande aux organisations d’utiliser des versions récentes de Windows 10 avec une configuration de jointure Azure AD ou de jointure de domaine hybride. Ceci garantit que les comptes des utilisateurs sont répertoriés dans le gestionnaire de comptes web de Windows, ce qui permet d’activer l’authentification unique pour Teams et les autres applications Microsoft. Cela offre une expérience utilisateur améliorée (connexion silencieuse) et une meilleure position en matière de sécurité.

Microsoft Teams utilise l’authentification moderne pour simplifier et sécuriser l’expérience de connexion. Pour voir comment les utilisateurs se connectent à Teams, consultez [Se connecter à Teams](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055).

## <a name="how-modern-authentication-works"></a>Fonctionnement de l’authentification moderne

L’authentification moderne est un processus qui permet à Teams de s’informer que les utilisateurs ont déjà entré leurs informations d’identification (par e-mail et mot de passe professionnels), et ne doivent pas être obligés de les entrer à nouveau pour démarrer l’application. L’expérience peut varier en fonction de plusieurs facteurs, par exemples, si les utilisateurs travaillent dans Windows ou sur un Mac. Il peut également varier selon que votre organisation a activé l’authentification à facteur unique ou l’authentification multi-facteur (l’authentification multi-facteur implique généralement de vérifier les informations d’identification par téléphone, en fournissant un code unique, en entrant un code confidentiel ou présentation d’une empreinte numérique). Voici un récapitulatif de chaque scénario d’authentification moderne.

### <a name="windows-users"></a>Utilisateurs Windows

- Si des utilisateurs ont déjà ouvert une session sur Windows ou d’autres applications Office via leur compte professionnel ou scolaire, ils sont directement dirigés vers l’application lorsqu’ils démarrent Teams. Il ne leur est pas nécessaire d’entrer leurs informations d’identification.

- Microsoft recommande d’utiliser Windows 10 version 1903 ou ultérieure pour optimiser l’expérience d’authentification unique.

- Si les utilisateurs ne sont pas connectés à leur compte professionnel ou scolaire en tout lieu, lorsqu’ils démarrent Teams, ils sont invités à fournir une authentification à un ou plusieurs facteurs (SFA ou MFA), en fonction de ce que votre organisation a décidé de vouloir processus.

- Si les utilisateurs sont connectés à un ordinateur joint à un domaine, lorsqu’ils démarrent Teams, ils peuvent être invités à effectuer une étape d’authentification supplémentaire, selon que votre organisation a choisi d’utiliser l’authentification multi-facteur ou si son ordinateur nécessite déjà l’authentification multi-facteur pour se connecter. Si l’ordinateur requiert déjà l’authentification multi-facteur, lorsqu’il ouvre Teams, l’application démarre automatiquement.

- Sur les PC joints à un domaine, lorsque l’authentification unique est impossible, Teams peut pré-remplir l’écran de connexion à l’aide du nom d’utilisateur principal (UPN). Il peut arriver que vous ne souhaitiez pas utiliser cette option dans certains cas, notamment si votre organisation utilise différents noms d’utilisateur principal localement et dans Azure Active Directory. Dans ce cas, vous pouvez utiliser la clé de Registre Windows suivante pour désactiver le pré-remplissage du nom d’utilisateur principal :

  Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams<br/>
  SkipUpnPrefill(REG_DWORD)<br/>
  0x00000001 (1)

    > [!NOTE]
    > Lorsque vous ignorez ou ignorez le nom d’utilisateur, les noms d’utilisateur qui se terminent par « . local » ou « . Corp » sont activés par défaut. vous n’avez donc pas besoin de définir une clé de Registre pour les désactiver.


### <a name="mac-users"></a>Utilisateurs Mac

Sur MacOS, Teams invite les utilisateurs à entrer leur nom d’utilisateur et informations d’identification, et peut demander l’authentification multifacteur selon les paramètres de votre organisation. Une fois que les utilisateurs ont entré leurs informations d’identification, ils ne sont pas obligés de les redonner. À partir de ce point, Teams démarre automatiquement chaque fois qu’ils travaillent sur le même ordinateur.

## <a name="switching-accounts-after-completing-modern-authentication"></a>Changer de compte une fois l’authentification moderne terminée

Si les utilisateurs travaillent sur un ordinateur joint au domaine (par exemple, si leur client a activé Kerberos), ils ne peuvent pas changer de compte d’utilisateur une fois l’authentification moderne terminée. Si les utilisateurs ne travaillent pas sur un ordinateur joint à un domaine, ils peuvent changer de compte.

## <a name="signing-out-of-teams-after-completing-modern-authentication"></a>Déconnexion de Teams après l’exécution de l’authentification moderne

Pour se déconnecter de Teams, les utilisateurs peuvent cliquer sur leur image de profil dans la partie supérieure de l’application, puis sélectionner **se déconnecter**. Ils peuvent également cliquer avec le bouton droit sur l’icône de l’application dans la barre des tâches, puis sélectionner **se déconnecter**. Une fois qu’ils se déconnectent de Teams, ils doivent ré-entrer leurs informations d’identification pour lancer l’application.

## <a name="urls-and-ip-address-ranges"></a>URL et plages d’adresses IP

Teams a besoin d’une connexion à Internet. Pour comprendre les points de terminaison pouvant être atteints pour les clients qui utilisent Teams dans Office 365 plans, secteur public et autres nuages, consultez [URL et plages d’adresses IP d’Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).

> [!IMPORTANT]
> Pour l’instant, Teams a besoin d’accéder (port TCP 443) au service Google ssl.gstatic.com (<https://ssl.gstatic.com)> pour tous les utilisateurs, c’est vrai même si vous n’utilisez pas Gstatic. Teams supprimera cette exigence prochainement (début 2020). nous mettrons à jour cet article en conséquence.

## <a name="troubleshooting-modern-authentication"></a>Résolution des problèmes d’authentification moderne

L’authentification moderne est disponible pour toutes les organisations qui utilisent Teams. par conséquent, si les utilisateurs ne parviennent pas à terminer le processus, il se peut qu’il y ait un problème avec votre domaine ou le compte scolaire ou professionnel de votre organisation.

Pour plus d’informations, voir [Pourquoi est-ce que je rencontre des problèmes pour me connecter à Microsoft Teams ?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)
