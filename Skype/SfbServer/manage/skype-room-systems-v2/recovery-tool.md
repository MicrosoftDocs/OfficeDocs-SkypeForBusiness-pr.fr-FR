---
title: Utiliser l’outil de récupération de systèmes de salle Skype v2
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 4/17/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df418e25-81fd-474d-be16-5cd1ac8145cc
description: Cet article explique comment utiliser l’outil de récupération pour systèmes de salle Skype v2, ce qui permet de mettre un système obsolète dans un état pris en charge.
ms.openlocfilehash: 5972f38370227e93cb0154771a35f3c5b0458052
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/18/2018
---
# <a name="use-the-skype-room-systems-v2-recovery-tool"></a>Utiliser l’outil de récupération de systèmes de salle Skype v2
 
Cet article explique comment utiliser l’outil de récupération pour systèmes de salle Skype v2, ce qui permet de mettre un système obsolète dans un état pris en charge. Vous utilisez cet outil lorsque la console de v2 Skype salle systèmes affiche une erreur « la configuration système obsolète ».
  

<a name="Prerequisites"> </a>  
## <a name="prerequisites"></a>Conditions requises

Téléchargez le dernier [package d’installation de systèmes de salle Skype v2](https://go.microsoft.com/fwlink/?linkid=851168) et extrayez-le sur un USB mémoire stick ou un partage réseau accessible au périphérique v2 systèmes de salle de Skype.

Vous devez également installer [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).

<a name="Windows-ver"> </a>
## <a name="verify-windows-version"></a>Vérifier la Version de Windows 

1. Connexion à un compte d’administrateur à partir de **Paramètres > Paramètres Windows > Admin signe dans** à partir du périphérique de v2 de systèmes de salle de Skype. Cette option affiche l’écran de connexion.
2. Connexion à un compte d’administrateur, l’administrateur par défaut compte étant `admin` avec le mot de passe `sfb`.
3. Cliquez sur le menu Démarrer et le type `winver.exe` dans la zone de recherche et cliquez sur **Commande Exécuter* dans le résultat.
4. Notez le numéro après 'Version' sur la deuxième ligne du volet d’informations.

> [REMARQUE] Si la Version indiquée est 1607 ou version antérieure, suivez les étapes de la procédure de <a href="#Windows-up">Mise à jour de Windows avant la restauration</a> avant de poursuivre les étapes à <a href="#Perform">effectuer une restauration</a> . Si la Version indiquée est supérieure à 1607, suivez uniquement les étapes de <a href="#Perform">effectuer une restauration</a>.

<a name="Windows-up"> </a>
## <a name="update-windows-before-recovery-if-needed"></a>Mise à jour de Windows avant la restauration (si nécessaire)

1. Bien que toujours connecté tant qu’utilisateur admin, lancez une invite de commandes avec élévation de privilèges Powershell.
2. Exécutez la commande `Remove-Item -Path 'c:\Recovery\OEM\$oem$\$1\Rigel' -Force -Recurse`.
3. Exécutez Windows Update et installer la mise à jour pour Windows 1709.
4. Une fois la mise à jour 1709 signe complète dans admin compte et installer [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu). La mise à jour peut être effectuée à partir du lien ou à l’aide de Windows Update.
5. Installer les mises à jour supplémentaires disponibles à partir de Windows Update.

<a name="Perform"> </a>
## <a name="perform-a-recovery"></a>Effectuer une restauration

1. Connectez-vous au compte administrateur sur votre appareil v2 de systèmes de salle Skype et lancer une invite de commandes avec élévation de privilèges.
2. Vérifiez à partir du périphérique de v2 Skype salle systèmes que vous ne pouvez accéder à la `RecoveryTool.ps1` fichier, ce qui est inclus dans les fichiers extraits à partir du package d’installation de systèmes de salle Skype v2. Vous trouverez le kit sur le partage réseau ou un lecteur USB utilisé lors de la préparation des conditions préalables.
3. Exécutez la commande Powershell.exe `-file "<path to RecoveryTool.ps1>" -ExecutionPolicy Unrestricted`.
4. Lorsque vous y êtes invité par l’option de sélection de script `1:"Repair System"`.
5. À la fin, redémarrez le périphérique v2 de systèmes de salle de Skype. Il redémarre à nouveau automatiquement et élaborer totalement récupéré la deuxième fois.



<a name="See"> </a>  
## <a name="see-also"></a>Voir aussi


#### 

[Gérer l’espace de Skype systèmes v2](skype-room-systems-v2.md)
#### 