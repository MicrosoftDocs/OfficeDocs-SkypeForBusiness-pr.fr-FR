---
title: Se connecter à des équipes de Microsoft
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/23/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ''
description: Conseils pour vous connecter à Microsoft Teams à l’aide de l’authentification moderne.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6ab460b848bff27d8aeabc643e34082eaa25d5ae
ms.sourcegitcommit: 39228142658557890b2173c41db9661eb502b946
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
<a name="sign-in-to-microsoft-teams"></a>Se connecter à des équipes de Microsoft
==========================

Teams de Microsoft utilise une authentification moderne pour conserver l’expérience de connexion simple et sécurisée.

## <a name="how-modern-authentication-works"></a>Comment modernes de fonctionnement de l’authentification

Authentification moderne est un processus qui permet aux équipes de savoir que les utilisateurs ont déjà entré leurs informations d’identification (par exemple leur messagerie électronique et un mot de passe), ailleurs, et ils ne doivent pas être doit entrer à nouveau afin de démarrer l’application. L’expérience dépend de plusieurs facteurs, tels que si les utilisateurs travaillent dans Windows ou sur un Mac. Elle varie également selon que votre organisation a activé l’authentification unifactorielle ou plusieurs facteurs d’authentification (plusieurs facteurs d’authentification implique généralement la vérification des informations d’identification via un téléphone, en fournissant un code unique, en entrant un code confidentiel, ou présentation d’une empreinte numérique). Voici un récapitulatif de chaque scénario d’authentification modernes.

### <a name="windows-users"></a>Utilisateurs de Windows 

- Si les utilisateurs ont déjà signé à d’autres applications Office, par l’intermédiaire de leur compte Office 365 Enterprise, lorsqu’ils démarrent des équipes, ils sont immédiatement amenés à l’application. Il n’a pas besoin d’entrer leurs informations d’identification.

- Si les utilisateurs ne sont pas signés leur compte Office 365 Enterprise n’importe où ailleurs, lorsqu’ils démarrent des équipes, ils êtes invités à fournir les soit unique ou plusieurs facteur d’authentification (SFA ou AMF), en fonction de ce que votre organisation a décidé qu’ils aimeraient le processus d’entraîner.

- Si les utilisateurs sont connectés à un ordinateur à un domaine, lorsqu’ils démarrent des équipes, ils vous serez peut-être invités à traverser une étape supplémentaire pour l’authentification en fonction de si votre organisation a opté pour exiger AMF ou si leur ordinateur requiert déjà AMF pour vous connecter. Si leur ordinateur requiert déjà AMF pour vous connecter, lorsqu’il ouvre des équipes, l’application automatiquement démarre.

### <a name="mac-users"></a>Utilisateurs de Mac 

Lorsque les utilisateurs démarrent des équipes, leur ordinateur ne sera en mesure d’extraire leurs informations d’identification de leur compte Office 365 Enterprise ou l’un de leurs autres applications Office. Au lieu de cela, ils verront un message demandant les SFA ou AMF (selon les paramètres de votre organisation). Une fois que les utilisateurs entrent leurs informations d’identification, elles ne sont pas requises pour leur donner à nouveau. À ce stade, les équipes automatiquement démarre chaque fois qu’il travaillait sur le même ordinateur.

## <a name="switching-accounts-after-completing-modern-authentication"></a>Comptes de commutation d’authentification moderne à la fin

Si les utilisateurs travaillent sur un ordinateur à un domaine (par exemple, si leurs clients a activé Kerberos), ils ne peuvent pas basculer les comptes d’utilisateurs une fois qu’ils ont effectuées d’authentification moderne. Si les utilisateurs ne travaillent pas sur un ordinateur à un domaine, ils peuvent changer de compte.

## <a name="signing-out-of-microsoft-teams-after-completing-modern-authentication"></a>La déconnexion de Microsoft Teams la fin de l’authentification moderne

Pour vous déconnecter des équipes, les utilisateurs peuvent cliquez sur leur image de profil en haut de l’application et puis sélectionnez **déconnexion**. Ils peuvent également droit sur l’icône de l’application dans la barre des tâches et puis sélectionnez **Déconnecter**. Une fois qu’ils ont Déconnectez-vous des équipes, ils doivent entrer leurs informations d’identification pour lancer l’application.

## <a name="troubleshooting-modern-authentication"></a>Résolution des problèmes d’authentification moderne

Authentification moderne est disponible pour chaque organisation qu’utilise des équipes, si les utilisateurs ne sont pas en mesure de terminer le processus, il peut donc une anomalie avec votre domaine ou un compte Office 365 entreprise de votre organisation. 

Pour plus d’informations, consultez [pourquoi j’éprouve des difficultés à l’ouverture de session Microsoft Teams ?](https://support.office.com/en-US/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f).

