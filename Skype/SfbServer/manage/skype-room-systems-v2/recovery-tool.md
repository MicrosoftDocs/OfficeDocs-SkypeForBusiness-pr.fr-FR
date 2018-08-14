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
description: Cet article explique comment utiliser l’outil de récupération pour les systèmes de salle Skype v2, que vous utilisez pour intégrer un système obsolète à un état pris en charge.
ms.openlocfilehash: cd8e05be686cef1df44f364c515a6116edf06209
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/19/2018
ms.locfileid: "19504977"
---
# <a name="use-the-skype-room-systems-v2-recovery-tool"></a>Utiliser l’outil de récupération de systèmes de salle Skype v2
 
Cet article explique comment utiliser l’outil de récupération pour les systèmes de salle Skype v2, que vous utilisez pour intégrer un système obsolète à un état pris en charge. Vous utiliserez cet outil lorsque la console de v2 Skype salle systèmes indique une erreur « configuration de système obsolète ».
  

<a name="Prerequisites"> </a>  
## <a name="prerequisites"></a>Conditions requises

Télécharger le dernier [package d’installation de systèmes de salle Skype v2](https://go.microsoft.com/fwlink/?linkid=851168) et extrayez-le sur un USB mémoire module ou un partage réseau accessible à l’appareil v2 de systèmes de salle Skype.

Vous devez également installer [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).

<a name="Windows-ver"> </a>
## <a name="verify-windows-version"></a>Vérifier la Version de Windows 

1. Connexion à un compte d’administrateur en accédant à **Paramètres > Paramètres Windows > Admin Sign In** à partir de l’appareil v2 Skype salle systèmes. Cette option affiche l’écran de connexion.
2. Compte de la connexion à un compte d’administration, l’administrateur par défaut est `admin` avec le mot de passe `sfb`.
3. Cliquez sur le menu Démarrer et le type `winver.exe` dans la zone de recherche et cliquez sur * le résultat de la*Commande Exécuter* .
4. Notez le numéro après « Version » sur la deuxième ligne du volet d’informations.

>[!NOTE]
>Si la Version indiquée est 1607 ou une version antérieure, suivez les étapes dans les étapes de <a href="#Windows-up">Mise à jour Windows avant de récupération</a> avant de commencer les étapes à <a href="#Perform">effectuer une récupération</a> . Si la Version indiquée est supérieure à 1607, suivez uniquement les étapes dans <a href="#Perform">effectuer une récupération</a>.

<a name="Windows-up"> </a>
## <a name="update-windows-before-recovery-if-needed"></a>Mettre à jour Windows avant récupération (si nécessaire)

1. Alors que toujours connecté en tant qu’utilisateur admin, lancez une invite de commandes Powershell avec élévation de privilèges.
2. Exécutez la commande `Remove-Item -Path 'c:\Recovery\OEM\$oem$\$1\Rigel' -Force -Recurse`.
3. Exécutez Windows Update et installez la mise à jour pour Windows 1709.
4. Une fois la mise à jour 1709 connexion complète dans le compte d’administrateur et installer [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu). La mise à jour peut être effectuée à partir du lien ou à l’aide de Windows Update.
5. Comme une étape facultative, installez les mises à jour supplémentaires disponibles à partir de Windows Update.

<a name="Perform"> </a>
## <a name="perform-a-recovery"></a>Effectuer une récupération

1. Se connecter au compte d’administrateur sur votre appareil v2 de systèmes de salle Skype et lancez une invite de commandes avec élévation de privilèges.
2. Vérifiez de l’appareil v2 de systèmes de salle Skype que vous êtes en mesure d’accéder à la `RecoveryTool.ps1` fichier, qui est inclus dans les fichiers extraits à partir du package d’installation v2 Skype salle systèmes. Le kit se trouvent sur le partage réseau ou d’une clé USB utilisé lors de la préparation des conditions préalables.
3. Exécutez la commande Powershell.exe `-ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.
4. Lorsque vous êtes invité à l’option select script `1:"Repair System"`.
5. Une fois terminée, redémarrez l’équipement de v2 Skype salle systèmes. Il redémarre automatiquement et élaborer entièrement récupérée la deuxième fois.



<a name="See"> </a>  
## <a name="see-also"></a>Voir aussi
 
[Systèmes de salle Skype version 2](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Gestion de Skype Room System v2](skype-room-systems-v2.md)