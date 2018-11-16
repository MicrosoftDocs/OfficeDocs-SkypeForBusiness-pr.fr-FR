---
title: Se connecter à Microsoft Teams utilisant l’authentification moderne
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 11/15/2018
audience: Admin
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: Comment établir une connexion à Microsoft Teams en utilisant l’authentification moderne.
localization_priority: Normal
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 01ca138aebae8d0db731118baf3e340aa3332120
ms.sourcegitcommit: bd32d44d27990e373ce6afa38897159473601113
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2018
ms.locfileid: "26544371"
---
<a name="sign-in-to-microsoft-teams-using-modern-authentication"></a>Se connecter à Microsoft Teams utilisant l’authentification moderne
==========================

Teams Microsoft utilise l’authentification moderne pour conserver l’expérience de connexion simple et sécurisé. Pour voir comment les utilisateurs se connectent aux équipes, lisez [se connecter aux équipes](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055).

## <a name="how-modern-authentication-works"></a>Fonctionnement de l’authentification comment moderne

Authentification moderne est un processus qui permet aux équipes de savoir que les utilisateurs ont déjà entré leurs informations d’identification (comme leur messagerie électronique et le mot de passe) ailleurs, et ils ne doivent pas être invités à saisir à nouveau afin de démarrer l’application. L’expérience varie en fonction de plusieurs facteurs, tels que si les utilisateurs travaillent dans Windows ou sur un Mac. Il sera également varient selon que votre organisation a activé l’authentification unique facteurs ou l’authentification multifacteur (l’authentification multifacteur implique généralement la vérification des informations d’identification via un téléphone, en fournissant un code unique, en entrant un code confidentiel, ou présentation d’une empreinte numérique). Voici un récapitulatif de chaque scénario d’authentification moderne.

### <a name="windows-users"></a>Utilisateurs de Windows 

- Si les utilisateurs ont déjà connecté à d’autres applications Office par le biais de leur compte Office 365 pour entreprises, lorsqu’ils démarrent équipes qu’ils sont prises droits pour l’application. Il n’est pas nécessaire pour pouvoir entrer leurs informations d’identification.

- Si les utilisateurs n’êtes pas connectés à leur compte Office 365 pour entreprises ailleurs, lorsqu’ils démarrent équipes, ils êtes invités à fournir une authentification multifacteur soit seul facteur (SFA ou MFA), selon que votre organisation a décidé qu’il souhaite le processus entraîner.

- Si les utilisateurs sont connectés à un ordinateur à un domaine, lorsqu’ils démarrent équipes, ils peuvent être invités à passer par une étape supplémentaire pour l’authentification selon que votre organisation opté pour exiger que MFA ou si leur ordinateur requiert déjà MFA pour vous connecter. Si leur ordinateur requiert déjà MFA pour vous connecter, lorsqu’ils ouvrent les équipes, l’application automatiquement commence.

### <a name="mac-users"></a>Utilisateurs Macintosh 

Lorsque les utilisateurs démarrent les équipes, son ordinateur sera en mesure d’extraire leurs informations d’identification à partir de leur compte Office 365 pour entreprises ou l’un de leurs autres applications Office. Au lieu de cela, ils verront un message demandant les SFA ou MFA (selon les paramètres de votre organisation). Une fois que les utilisateurs entrent leurs informations d’identification, ils ne sont pas requises pour leur donner à nouveau. À ce stade, les équipes automatiquement démarre chaque fois qu’ils travaillez sur le même ordinateur.

## <a name="switching-accounts-after-completing-modern-authentication"></a>Comptes de commutation après la fin de l’authentification moderne

Si les utilisateurs travaillent sur un ordinateur à un domaine (par exemple, si leur client a activé Kerberos), ils ne peuvent pas passer des comptes d’utilisateur une fois qu’ils ont effectuées authentification moderne. Si les utilisateurs ne travaillent pas sur un ordinateur à un domaine, ils peuvent changer de compte.

## <a name="signing-out-of-microsoft-teams-after-completing-modern-authentication"></a>Déconnexion de Microsoft Teams après la fin de l’authentification moderne

Pour vous déconnecter d’équipes, les utilisateurs peuvent cliquez sur l’image en haut de l’application de leur profil, puis sélectionnez **se déconnecter**. Ils peuvent également avec le bouton droit de l’icône d’application dans la barre des tâches, puis sélectionnez **se déconnecter**. Une fois qu’ils ont connexion en dehors des équipes, ils doivent entrer leurs informations d’identification pour lancer l’application.

## <a name="troubleshooting-modern-authentication"></a>Résolution des problèmes d’authentification moderne

Authentification moderne est disponible pour chaque organisation qu’utilise les équipes, donc si les utilisateurs ne sont pas en mesure de terminer le processus, il peut exister une anomalie avec votre compte de domaine ou de votre organisation Office 365 pour entreprises. 

Pour plus d’informations, voir [Pourquoi ai-je des problèmes de connexion à Microsoft Teams ?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f).

