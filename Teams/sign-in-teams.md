---
title: Se connecter à Microsoft Teams en utilisant l’authentification moderne
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 11/15/2018
audience: Admin
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: Se connecter à Microsoft teams à l’aide de l’authentification moderne.
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9911a014fe3bd3e3ede151e2a85e8181c399e463
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41790612"
---
<a name="sign-in-to-microsoft-teams-using-modern-authentication"></a>Se connecter à Microsoft Teams en utilisant l’authentification moderne
==========================

Microsoft teams utilise l’authentification moderne pour garantir une connexion simple et sécurisée. Pour savoir comment les utilisateurs se connecter à Teams, voir [se connecter à teams](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055).

## <a name="how-modern-authentication-works"></a>Fonctionnement de l’authentification moderne

L’authentification moderne est un processus qui permet à teams de savoir que les utilisateurs ont déjà entré leurs informations d’identification (par exemple, leur adresse de courrier professionnelle et leur mot de passe), et qu’ils ne doivent plus être obligés de les entrer à nouveau pour démarrer l’application. L’utilisation peut varier en fonction de quelques facteurs, par exemple si les utilisateurs travaillent dans Windows ou sur un Mac. Il peut également varier selon que votre organisation a activé l’authentification à un seul facteur ou l’authentification multifacteur (l’authentification multifacteur implique généralement de vérifier les informations d’identification par le biais d’un téléphone, de fournir un code unique, d’entrer un code confidentiel ou présentation d’une empreinte digitale. Vous trouverez ci-dessous un récapitulatif de chaque scénario d’authentification moderne.

### <a name="windows-users"></a>Utilisateurs de Windows 

- Si les utilisateurs ont déjà été connectés à d’autres applications Office par le biais de leur compte Office 365 entreprise, au moment où ils redémarrent Teams, ils sont dirigés directement vers l’application. Il n’est pas nécessaire d’entrer leurs informations d’identification.

- Si les utilisateurs ne sont pas connectés à leur compte Office 365 entreprise, où qu’ils soient, ils doivent fournir une authentification à un seul facteur ou multifacteur (SFA ou MFA), en fonction de ce que votre organisation a décidé d’utiliser pour la processus à comprendre.

- Si les utilisateurs sont connectés à un ordinateur appartenant à un domaine au démarrage d’Teams, ils peuvent être invités à procéder à une autre étape d’authentification, selon que votre organisation a opté pour l’authentification multifacteur ou si elle exige déjà une authentification multifacteur pour se connecter. Si son ordinateur exige déjà une authentification multifacteur, il démarre automatiquement lorsque les utilisateurs ouvrent Teams.

- Si les utilisateurs sont connectés à un ordinateur appartenant à un domaine et que vous ne souhaitez pas que leur nom d’utilisateur soit prérempli sur l’écran de connexion Teams, les administrateurs peuvent configurer le Registre Windows suivant pour désactiver le pré-remplissage du nom d’utilisateur : ordinateur \ HKEY_CURRENT_USER \Software\ Microsoft\Office\Teams DisableUpnSuffixCheck (REG_DWORD) 0x00000001 (1)

  Remarque : le préremplissage du nom d’utilisateur qui se termine par « . local » ou « . Corp » est activé par défaut, de sorte que vous n’avez pas besoin de définir une clé de Registre pour désactiver cette fonctionnalité. 


### <a name="mac-users"></a>Utilisateurs de Mac 

Lorsque l’utilisateur démarre Teams, son ordinateur ne peut pas extraire ses informations d’identification à partir de son compte Office 365 entreprise ou de ses autres applications Office. À la place, une invite s’affiche pour vous demander de SFA ou d’authentification multifacteur (en fonction des paramètres de votre organisation). Lorsque l’utilisateur saisit ses informations d’identification, il ne doit plus être tenu de le fournir. À partir de ce point, teams démarre automatiquement chaque fois qu’il travaille sur le même ordinateur.

## <a name="switching-accounts-after-completing-modern-authentication"></a>Changer de compte après avoir effectué une authentification moderne

Si les utilisateurs travaillent sur un ordinateur appartenant à un domaine (par exemple, si le client a activé Kerberos), il ne peut pas changer de compte d’utilisateur après avoir effectué une authentification moderne. Si les utilisateurs ne travaillent pas sur un ordinateur appartenant à un domaine, ils peuvent changer de compte.

## <a name="signing-out-of-microsoft-teams-after-completing-modern-authentication"></a>Déconnexion de Microsoft teams après avoir terminé l’authentification moderne
Pour vous déconnecter de teams, les utilisateurs peuvent cliquer sur leur image de profil en haut de l’application, puis sélectionnez **se déconnecter**. Ils peuvent également cliquer avec le bouton droit sur l’icône de l’application dans la barre des tâches, puis sélectionner **se déconnecter**. Une fois qu’il se déconnecter de teams, il doit entrer de nouveau ses informations d’identification pour lancer l’application.

## <a name="urls-and-ip-address-ranges"></a>URL et plages d’adresses IP
Teams nécessite une connexion à Internet. Pour comprendre les points de terminaison qui doivent être accessibles pour les clients qui utilisent des équipes dans les plans Office 365, le gouvernement et les autres nuages, consultez les [conseils disponibles ici](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges). En plus de cela, vous devez également autoriser l’accès à https://ssl.gstatic.com.

## <a name="troubleshooting-modern-authentication"></a>Résolution des problèmes d’authentification moderne

L’authentification moderne est disponible pour toutes les organisations qui utilisent Teams, de sorte que si les utilisateurs ne sont pas en mesure de terminer le processus, il se peut qu’il y ait un problème au niveau de votre domaine ou du compte Office 365 entreprise de votre organisation. 

Pour plus d’informations, reportez-vous à la section [pourquoi je rencontre des difficultés pour me connecter à Microsoft teams ?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f).

