---
title: Utiliser l’outil de récupération de Microsoft Teams Rooms
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: sohailta
ms.date: 4/17/2018
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
localization_priority: Normal
description: Cet article explique comment utiliser l’outil de récupération pour les salles de Microsoft Teams, que vous utiliseriez pour mettre à jour un système obsolète dans un État pris en charge.
ms.openlocfilehash: bc35dc744dac5f04d537f023e790bc89c2c649d0
ms.sourcegitcommit: 70bf1669442bbb50cb293c86d6a0c80fb3b2b55a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2019
ms.locfileid: "38675348"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a>Utiliser l’outil de récupération de Microsoft Teams Rooms
 
Cet article explique comment utiliser l’outil de récupération pour les salles de Microsoft Teams, que vous utiliseriez pour mettre à jour un système obsolète dans un État pris en charge. Vous pouvez utiliser cet outil lorsque le message d’erreur « configuration système obsolète » s’affiche.
  

<a name="Prerequisites"> </a>  
## <a name="prerequisites"></a>Conditions requises

Téléchargez le dernier [package d’installation de Microsoft teams](https://go.microsoft.com/fwlink/?linkid=851168) , puis récupérez-le sur une clé USB ou un partage réseau accessible à partir de l’appareil Microsoft Teams.

Vous devrez également installer [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).

<a name="Windows-ver"> </a>
## <a name="verify-windows-version"></a>Vérifier la version de Windows 

1. Connectez-vous à un compte d’administrateur en accédant à **paramètres> paramètres de Windows> vous connecter** à l’administrateur à partir de l’appareil Microsoft Teams. Cette option vous permet d’accéder à l’écran de connexion.
2. Connectez-vous à un compte d’administrateur, `admin` à l’aide du compte `sfb`d’administrateur par défaut et du mot de passe.
3. Cliquez sur le menu Démarrer, puis `winver.exe` tapez dans la zone de recherche et cliquez sur la*commande + exécuter* du résultat.
4. Notez le numéro après « version » dans la deuxième ligne du volet d’informations.

>[!NOTE]
>Si la version présentée est 1607 ou une version antérieure, suivez les étapes de la procédure de <a href="#Windows-up">mise à jour de Windows avant la récupération</a> avant de procéder à la <a href="#Perform">récupération</a> . Si la version présentée est supérieure à 1607, procédez comme suit pour <a href="#Perform">effectuer une récupération</a>.

<a name="Windows-up"> </a>
## <a name="update-windows-before-recovery-if-needed"></a>Mise à jour de Windows avant la récupération (si nécessaire)

1. Quand vous êtes connecté en tant qu’administrateur, lancez une invite PowerShell avec élévation de privilèges.
2. Exécutez la commande `Remove-Item -Path 'c:\Recovery\OEM\$oem$\$1\Rigel' -Force -Recurse`.
3. Exécutez Windows Update et installez la mise à jour pour Windows 1709.
4. À l’issue de la mise à jour vers 1709, reconnectez-vous au compte d’administrateur, puis installez [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu). La mise à jour est possible à partir du lien ou à l’aide de Windows Update.
5. Installez éventuellement des mises à jour supplémentaires disponibles à partir de Windows Update.

<a name="Perform"> </a>
## <a name="perform-a-recovery"></a>Effectuer une récupération

1. Connectez-vous au compte d’administrateur sur votre appareil Microsoft Teams, puis lancez une invite de commandes avec élévation de privilèges.
2. Vérifiez à partir de l’appareil de Microsoft teams que vous êtes en `RecoveryTool.ps1` mesure d’accéder au fichier, qui est inclus dans les fichiers extraits du package d’installation de Microsoft Teams. Le kit est disponible sur le partage réseau ou sur le lecteur USB utilisé pour préparer les éléments requis.
3. Exécutez la commande `-ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`PowerShell. exe.
4. Lorsque vous y êtes invité par l’option `1:"Repair System"`de sélection de script.
5. Lorsque vous avez terminé, redémarrez l’appareil Microsoft Teams. Elle redémarrera automatiquement et sera entièrement récupérée la deuxième fois.



<a name="See"> </a>  
## <a name="see-also"></a>Voir aussi
 
[Aide Microsoft Teams Rooms](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Gérer Microsoft Teams Rooms](skype-room-systems-v2.md)
