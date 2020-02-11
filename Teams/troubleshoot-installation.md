---
title: Résoudre les problèmes d’installation et de mise à jour de Microsoft teams sur Windows
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: lenatarhun
ms.topic: article
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment résoudre les problèmes d’installation et de mise à jour de l’application application de bureau teams sur Windows.
ms.openlocfilehash: 5c6ee4da7e4bb78463cb262cb382e3a090529bb5
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888843"
---
# <a name="troubleshoot-microsoft-teams-installation-and-update-issues-on-windows"></a>Résoudre les problèmes d’installation et de mise à jour de Microsoft teams sur Windows

Cet article fournit des conseils pour diagnostiquer et résoudre les problèmes d’installation et de mise à jour de l’application de bureau teams client en cours d’exécution sur Windows.

## <a name="check-whether-teams-is-updated-successfully"></a>Vérifier si teams a été correctement mis à jour

Suivez ces étapes pour vérifier si une mise à jour d’équipes est correctement installée.

1. Dans équipes, sélectionnez votre image de profil, puis cliquez sur **à propos de** > la**version**.
2. Dans le menu contextuel, cliquez sur **Rechercher les mises à jour**.
3. Attendez la bannière située dans la partie supérieure de l’application pour indiquer que le « rafraîchissement » de teams est nécessaire. Le lien doit s’afficher pendant une minute plus tard dans la mesure où ce processus télécharge la nouvelle version d’Teams. La bannière vous permet également de savoir si vous utilisez déjà la version la plus récente, auquel cas vous n’avez pas besoin de mettre à jour.
4. Cliquez sur le lien Actualiser dans la bannière.
5. Attendez le redémarrage d’Teams, puis répétez l’étape 1 pour voir si l’application est mise à jour.

Si un message d’erreur s’affiche ou si le numéro de version est identique à celui de l’étape 4, le processus de mise à jour a échoué.

## <a name="troubleshoot-installation-and-update-issues"></a>Résoudre les problèmes d’installation et de mise à jour

### <a name="troubleshoot-installation-issues"></a>Résoudre les problèmes d’installation

Lorsque teams est installé, le programme d’installation d’équipes enregistre la séquence d’événements sur%LocalAppData%\SquirrelTemp\SquirrelSetup.log. La première chose à chercher est un message d’erreur ou une pile d’appels à proximité de la fin du journal. Notez que les piles d’appels au début du journal risquent de ne pas être à l’origine d’un problème d’installation. Il peut être plus facile de comparer votre journal aux journaux d’une installation réussie (même sur un autre ordinateur) pour voir ce qui est attendu.

Si SquirrelSetup. log n’indique pas la cause ou si vous avez besoin d’informations supplémentaires pour résoudre le problème, reportez-vous à la rubrique [collecter et analyser les journaux d’application et de système](#collect-and-analyze-application-and-system-logs).

### <a name="troubleshoot-update-issues"></a>Résoudre les problèmes de mise à jour

Lorsque teams est correctement installé, l’emplacement du journal passe de%LocalAppData%\SquirrelTemp à%AppData%\Microsoft\Teams. À cet emplacement, il existe deux fichiers journaux intéressants, SquirrelSetup. log et log. txt.

- Le fichier SquirrelSetup. log à cet emplacement est écrit par Update. exe, qui est un exécutable qui service l’application Teams.
- Le fichier logs. txt est utilisé par l’application Teams (spécialement Teams. exe) pour enregistrer des événements d’application importants. Il contient probablement des informations d’échec.

Ces fichiers journaux contiennent des informations d’identification personnelle qui ne sont pas envoyées à Microsoft.

Les équipes peuvent lancer le processus de mise à jour (en fonction de la stratégie) ou les utilisateurs peuvent rechercher manuellement les mises à jour en accédant à leur image de profil > **Rechercher les mises à jour**. Les deux méthodes utilisent la séquence d’événements suivante.

1. **Recherchez les mises à jour**. Teams effectue une demande Web et inclut la version actuelle de l’application et les informations de la sonnerie de déploiement. L’objectif de cette étape est d’obtenir le lien de téléchargement. Un échec à cette étape est consigné dans logs. txt.
2. **Télécharger la mise à jour**. Teams télécharge la mise à jour à l’aide du lien de téléchargement obtenu à partir de l’étape 1. Lorsque le téléchargement est terminé, teams appelle Update. exe pour effectuer le téléchargement. Un échec de téléchargement est également consigné dans logs. txt.
3. **Étape de la mise à jour**. Le contenu téléchargé est vérifié et décompressé dans un dossier intermédiaire,%LocalAppData%\Microsoft\Teams\stage), qui est exécuté par Update. exe. Les échecs à cette étape sont enregistrés dans SquirrelTemp. log.
4. **Installez la mise à jour**. Il existe plusieurs façons de démarrer Teams. Le système démarre automatiquement teams lorsqu’un utilisateur se connecte, ou vous pouvez démarrer teams par le biais d’un raccourci. Dans cette étape, Update. exe vérifie la présence du dossier intermédiaire, vérifie à nouveau le contenu et exécute les opérations de fichier pour désinstaller l’application. L’ancien dossier d’application dans%LocalAppData%\Microsoft\Teams\current est sauvegardé sur%LocalAppData%\Microsoft\Teams\previous et le dossier stage est renommé « Current ». Les échecs à cette étape sont enregistrés dans SquirrelTemp. log.

Si SquirrelTemp. log ou log. txt ne contient pas les informations suffisantes pour déterminer la cause sous-jacente et que vous avez besoin d’informations supplémentaires pour résoudre le problème, accédez à [collecter et analyser les journaux d’application et de système](#collect-and-analyze-application-and-system-logs).

## <a name="collect-and-analyze-application-and-system-logs"></a>Collecter et analyser les journaux d’application et de système

Cette section explique comment collecter et analyser les journaux d’application et de système pour obtenir des informations plus complètes pour résoudre ce problème. Pour effectuer ces étapes, vous devez utiliser les outils Sysinternals. Pour en savoir plus, voir [Windows Sysinternals](https://docs.microsoft.com/sysinternals/).

### <a name="collect-logs"></a>Collecter les journaux

1. Téléchargez les [Outils Sysinternals](https://download.sysinternals.com/files/SysinternalsSuite.zip).
2. Extrayez le fichier zip dans le dossier% TEMP% sur votre disque local.
3. Ouvrez une invite de commandes avec élévation de privilèges, puis procédez comme suit :

    1. Pour accéder à votre dossier TEMP, procédez comme suit :

        ```console
        cd /d %TEMP%
        ```
    2. Copiez les journaux de configuration et d’application. Notez que certains de ces journaux risquent de ne pas être présents en fonction du point de défaillance.

        ```console
        copy %LocalAppData%\SquirrelTemp\SquirrelSetup.log SquirrelSetup.log
        copy %AppData%\Microsoft\Teams\logs.txt logs.txt
        copy %LocalAppData%\Microsoft\Teams\SquirrelSetup.log SquirrelSetup_Teams.log
        ```
    3. Exécutez la commande suivante pour capturer les descripteurs ouverts.

        ```console
        handle > handles.txt
        ```

    4. Exécutez la commande suivante pour capturer les dll ouvertes.

        ```console
        listdlls -v Teams > dlls.txt
        ```
    5. Exécutez la commande suivante pour capturer les pilotes en cours d’exécution.

        ```console
        driverquery /v > driverquery.txt
        ```

    6. Exécutez la commande suivante pour capturer les listes de contrôle d’accès (ACL) du dossier Teams.

        ```console 
        icacls %LOCALAPPDATA%\Microsoft\Teams /save icacls.txt /T
        ```

### <a name="analyze-logs-for-advanced-users"></a>Analyser les journaux (pour les utilisateurs avancés)

Une mise à jour en échec peut entraîner un comportement inattendu de l’application. Par exemple, il se peut que les utilisateurs ne soient pas en mesure de sortir d’une équipe, d’une version obsolète d’une équipe ou de démarrer Teams. Si vous constatez un problème lors d’une mise à jour, le premier endroit où chercher la cause est SquirrelTemp. log. Voici les différents types d’échecs de mise à jour, classés du plus courant au moins courant, et comment analyser et résoudre les problèmes liés à l’utilisation de journaux.

#### <a name="unable-to-exit-teams"></a>Impossible de quitter teams

Lorsque teams détermine qu’il doit procéder à une mise à jour vers une version plus récente, il télécharge et met à jour la nouvelle application, puis attend qu’une opportunité s’y redémarre la prochaine fois que l’ordinateur est inactif. Un problème courant au cours de ce processus est lié à un autre processus ou pilote de système de fichiers qui verrouille le processus Teams. exe, qui empêche Teams. exe de sortir. Par conséquent, l’application Teams ne peut pas être remplacée par l’application que vous venez de télécharger et de intermédiaire.

Conseils de dépannage :

- Pour confirmer qu’il s’agit d’un problème que vous rencontrez, quittez Teams (cliquez avec le bouton droit sur teams dans la barre des tâches, puis cliquez sur **quitter**). Ensuite, ouvrez le gestionnaire des tâches dans Windows pour voir si une instance d’équipes est toujours en cours d’exécution.  
- Si vous n’êtes pas sur l’ordinateur qui rencontre ce problème, examinez le fichier SquirrelTemp. log qui est collecté sur l’ordinateur qui rencontre ce problème et recherchez un « programme : impossible de terminer le processus dans l’entrée journal ».
- Pour déterminer ce qui empêche Teams. exe de sortir, observez les journaux dll. txt et handles. txt. Les processus suivants vous indiquent les processus dont l’abandon d’une équipe a empêché.
- Un autre coupable qui peut empêcher les équipes de sortir est le pilote de filtre de système de fichiers en mode noyau. Utilisez l’outil SysInternals, [ProcDump](https://docs.microsoft.com/sysinternals/downloads/procdump), pour collecter le vidage du processus en mode noyau en ```procdump -mk <pid>```exécutant, <pid> où est l’ID de processus obtenu auprès du gestionnaire des tâches. Vous pouvez également examiner le fichier journal driverquery. txt pour afficher les pilotes de filtre actifs susceptibles d’interférer avec Teams.
- Pour résoudre ce problème, redémarrez l’ordinateur.

#### <a name="file-permissions"></a>Autorisations de fichier

Teams crée un certain nombre de sous-dossiers et de fichiers dans le profil de l’utilisateur tout au long du processus d’installation et de mise à jour. Dans la mesure où l’application et le programme de mise à jour s’exécutent en tant qu’utilisateur ne disposant pas de privilèges élevés, les autorisations de lecture et d’écriture doivent être accordées sur les dossiers suivants :

|Folder  |Utilisé par  |
|---------|---------|
|%LocalAppData%\SquirrelTemp     | Programme d’installation d’équipes (par exemple, Teams_Windows_x64. exe) lors de la phase d’installation        |
|%LocalAppData%\Microsoft\Teams  | Mises à jour de Teams (Update. exe) pour extraire et exécuter le package d’application au cours de la mise à jour        |
|%AppData%\Microsoft\Teams   |  Application Teams (Teams. exe) pour enregistrer les paramètres et les États des applications, ainsi que le package de mise à jour (pré-intermédiaire) Téléchargé       |

Si Teams ne peut pas accéder à un fichier, car celui-ci ne peut pas écrire dans un fichier, une autre application logicielle peut interférer ou une entrée de descripteur de sécurité peut limiter l’accès à un dossier.

Conseils de dépannage :

- Recherchez « accès refusé » dans SquirrelTemp. log ou logs. txt. Archivez ces fichiers pour voir s’il y a eu une tentative d’écriture dans un fichier qui a échoué.
- Ouvrez icacls. txt et recherchez l’entrée de contrôle d’accès effective (ACE) qui bloque les opérations d’écriture d’un utilisateur qui n’est pas administrateur. En règle générale, il s’agit de l’une des entrées DACL. Pour plus d’informations, consultez la [documentation de icacls](https://docs.microsoft.com/windows-server/administration/windows-commands/icacls).

#### <a name="file-corrupted"></a>Fichier endommagé

Dans certains cas, le logiciel de chiffrement peut modifier les fichiers dans le dossier%LocalAppData%\Microsoft\Teams, qui peut empêcher les équipes de démarrer. Cela peut se produire à tout moment, même lorsque l’application n’est pas mise à jour. Malheureusement, lorsqu’un fichier est endommagé, le seul moyen de récupérer cet état consiste à désinstaller et réinstaller Teams.

> [!NOTE]
> Si vous ne parvenez pas à déterminer la cause sous-jacente du problème en suivant l’une de ces étapes, vous voudrez peut-être essayer une session du [moniteur de processus](https://docs.microsoft.com/sysinternals/downloads/procmon) . Process Monitor est un outil Sysinternals qui enregistre l’accès au registre et au système de fichiers.

## <a name="related-topics"></a>Rubriques connexes

- [Obtenir des clients pour Teams](get-clients.md)
- [Mises à jour du client pour Teams](teams-client-update.md)