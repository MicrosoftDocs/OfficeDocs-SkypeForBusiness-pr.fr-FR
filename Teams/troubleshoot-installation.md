---
title: Résoudre les problèmes d’installation et de mise à jour de Microsoft Teams sur Windows
ms.author: mikeplum
author: MikePlumleyMSFT
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
ms.localizationpriority: high
search.appverid: MET150
description: Découvrez comment résoudre les problèmes d’installation et de mise à jour pour l’application client de bureau Teams sur Windows.
ms.openlocfilehash: d01c67c58a67ab0c52becdd54f0298ec0196704c
ms.sourcegitcommit: 79ada2140b110239deff96e4854ebd5dd9b77881
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2022
ms.locfileid: "66605853"
---
# <a name="troubleshoot-microsoft-teams-installation-and-update-issues-on-windows"></a>Résoudre les problèmes d’installation et de mise à jour de Microsoft Teams sur Windows

Cet article fournit des instructions sur la façon de diagnostiquer et de résoudre les problèmes d’installation et de mise à jour pour l’application de client de bureau Teams exécutée sur Windows. Pour plus d’informations sur la résolution des problèmes, voir [Résolution des problèmes Teams](/MicrosoftTeams/troubleshoot/teams).

## <a name="check-whether-teams-is-updated-successfully"></a>Vérifier si Teams est correctement mis à jour

Suivez ces étapes pour vérifier si une mise à jour de Teams est correctement installée.

1. Dans Teams, sélectionnez les points de suspension (**...**) en regard de votre image de profil, puis cliquez sur **À propos de** > **la version**. Une bannière s’affiche, indiquant la version actuelle de Teams et la date de sa dernière mise à jour. Par exemple, **vous avez Microsoft Teams Version 1.5.00.3806 (64-bit)-E. Cette version a été mise à jour pour la dernière fois le 16/2/2022**.
2. Ouvrez de nouveau le menu des points de suspension, puis cliquez sur **Rechercher les mises à jour**.
3. Attendez que la bannière située en haut de l’application indique qu’une « actualisation » de Teams est nécessaire. Le lien doit apparaître environ une minute plus tard, car ce processus télécharge la nouvelle version de Teams. La bannière vous indique également si vous utilisez déjà la version la plus récente, auquel cas aucune mise à jour n’est nécessaire.
4. Cliquez sur le lien actualiser dans la bannière.
5. Patientez jusqu’à ce que Teams redémarre, puis répétez l’étape 1 pour vérifier si l’application est mise à jour.

Si vous voyez un message d’échec ou si le numéro de version est le même que dans l’étape 4, le processus de mise à jour a échoué.

## <a name="troubleshoot-installation-and-update-issues"></a>Résoudre les problèmes d’installation et de mise à jour

### <a name="troubleshoot-installation-issues"></a>Résoudre les problèmes d’installation

Une fois Teams installé, le programme d’installation de Teams enregistre la séquence d’événements sur `%LocalAppData%\SquirrelTemp\SquirrelSetup.log`. La première chose à rechercher est le message d’erreur ou la pile d’appels à l’approche de la fin du journal. Notez que les piles d’appels au début du journal ne signifient peut-être pas qu’il existe un problème d’installation. Il peut être plus facile de comparer votre journal au journal d’une installation réussie (même sur un autre ordinateur) pour voir ce qui est prévu.

Si `%LocalAppData%\SquirrelTemp\SquirrelSetup.log` n’indique pas la cause ou si vous avez besoin d’informations supplémentaires pour résoudre le problème, consultez [Collecter et analyser les journaux des applications et du système](#collect-and-analyze-application-and-system-logs).

### <a name="troubleshoot-update-issues"></a>Résoudre les problèmes de mise à jour

Une fois Teams correctement installé, l’emplacement du journal passe de `%LocalAppData%\SquirrelTemp` à `%LocalAppData%\Microsoft\Teams\SquirrelSetup.log`. Un autre fichier journal intéressant est `%AppData%\Microsoft\Teams\logs.txt`.

- Le fichier `%LocalAppData%\Microsoft\Teams\SquirrelSetup.log` est écrit par `Update.exe`, qui est un exécutable qui prend en charge l’application Teams.
- Le fichier `%AppData%\Microsoft\Teams\logs.txt` est utilisé par l’application Teams (spécifiquement `Teams.exe`) pour enregistrer les événements importants de l’application. Il contient généralement des informations d’échec.

Ces fichiers journaux contiennent des informations d’identification personnelle (PII) et ne sont donc pas envoyés à Microsoft.

Teams peut démarrer automatiquement le processus de mise à jour (selon la stratégie), ou les utilisateurs peuvent rechercher manuellement les mises à jour en accédant au menu des points de suspension (**...**) en regard de leur image de profil, puis en sélectionnant **Rechercher les mises à jour**. Les deux méthodes utilisent la séquence d’événements suivante.

1. **Rechercher les mises à jour**. Teams effectuent une requête sur le Web et inclut la version actuelle de l’application et les informations relatives à l’anneau de déploiement. L’objectif de cette étape est d’obtenir le lien de téléchargement. Un échec à cette étape est consigné dans `%AppData%\Microsoft\Teams\logs.txt`.
2. **Télécharger la mise à jour.**. Teams télécharge la mise à jour à l’aide du lien de téléchargement obtenu à partir de l’étape 1. Une fois le téléchargement terminé, Teams appelle `Update.exe` pour indexer le téléchargement. Un échec de téléchargement est également consigné dans `%AppData%\Microsoft\Teams\logs.txt`.
3. **Mettez à jour la mise à jour**. Le contenu téléchargé est vérifié et décompressé dans un dossier intermédiaire, `%LocalAppData%\Microsoft\Teams\stage`), lequel est exécuté par `Update.exe`. Les échecs à cette étape sont consignés dans `%LocalAppData%\Microsoft\Teams\SquirrelSetup.log`.
4. **Installez la mise à jour**. Plusieurs méthodes s’offrent à vous pour démarrer Teams. Le système démarre automatiquement Teams lorsqu’un utilisateur se connecte ou vous pouvez démarrer Teams à l’aide d’un raccourci. Au cours de cette étape, `Update.exe` vérifie la présence du dossier intermédiaire, vérifie de nouveau le contenu et effectue les opérations de fichier pour annuler l’exécution de l’application. L’ancien dossier d’application dans `%LocalAppData%\Microsoft\Teams\current` est sauvegardé dans `%LocalAppData%\Microsoft\Teams\previous` et le dossier intermédiaire est renommé en `current`. Les échecs à cette étape sont consignés dans `%LocalAppData%\Microsoft\Teams\SquirrelSetup.log`.

Si `%LocalAppData%\Microsoft\Teams\SquirrelSetup.log` ou `%AppData%\Microsoft\Teams\logs.txt` ne contiennent pas assez d’informations pour déterminer la cause sous-jacente et que vous avez besoin d’informations supplémentaires pour résoudre le problème, accédez à [Collecter et analyser les journaux des applications et du système](#collect-and-analyze-application-and-system-logs).

## <a name="collect-and-analyze-application-and-system-logs"></a>Collecter et analyser les journaux des applications et du système

Cette section explique comment recueillir et analyser les journaux des applications et du système afin d’obtenir des informations plus complètes pour résoudre le problème. Vous utiliserez les outils Sysinternals pour effectuer ces étapes. Pour plus d’informations, voir [Windows Sysinternals](/sysinternals/).

### <a name="collect-logs"></a>Collectez les journaux

1. Téléchargez les [outils Sysinternals](https://download.sysinternals.com/files/SysinternalsSuite.zip).
2. Extraire le fichier zip dans le dossier `%Temp%` sur votre disque local.
3. Ouvrez une invite de commandes avec élévation de privilèges, puis procédez comme suit :

    1. Pour accéder à votre dossier `%Temp%`, exécutez la commande suivante :

        ```console
        cd /d %Temp%
        ```

    2. Notez que certains de ces journaux peuvent ne pas être présents en fonction du point d’échec.

        ```console
        copy %LocalAppData%\SquirrelTemp\SquirrelSetup.log SquirrelSetup.log
        copy %AppData%\Microsoft\Teams\logs.txt logs.txt
        copy %LocalAppData%\Microsoft\Teams\SquirrelSetup.log SquirrelSetup_Teams.log
        ```

    3. Exécutez la commande suivante pour capturer les poignées ouvertes.

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
        icacls %LocalAppData%\Microsoft\Teams /save icacls.txt /T
        ```

### <a name="analyze-logs-for-advanced-users"></a>Analyser les journaux (pour les utilisateurs avancés)

La mise à jour qui a échoué peut entraîner un comportement imprévisible de l’application. Par exemple, il est possible que les utilisateurs ne puissent pas quitter Teams, aient une version caduque de Teams ou ne puissent pas démarrer Teams. Si vous rencontrez un problème lors d’une mise à jour, le premier emplacement pour rechercher la cause est `%LocalAppData%\SquirrelTemp\SquirrelSetup.log`. Voici les différents types d’échecs de mise à jour, qui sont répertoriés du plus courant au moins courant, et comment les analyser et les résoudre à l’aide des journaux.

#### <a name="unable-to-exit-teams"></a>Impossible de quitter Teams

Au fur et à mesure que Teams détermine qu’il doit se mettre en à jour avec une version plus récente, il télécharge et passe à la nouvelle application, puis attend une opportunité pour redémarrer la prochaine fois que l’ordinateur est inactif. Un problème courant lors de ce processus est qu’un autre processus ou un pilote de système de fichiers verrouille le processus `Teams.exe`, lequel empêche `Teams.exe` de se fermer. Par conséquent, l’application Teams ne peut pas être remplacée par l’application nouvellement téléchargée et intermédiaire.

Conseils de dépannage :

- Pour confirmer qu’il s’agit du problème que vous rencontrez, quittez Teams (cliquez avec le bouton droit sur Teams dans la barre des tâches, puis cliquez sur **Quitter**). Ouvrez ensuite le Gestionnaire des tâches dans Windows pour voir si une instance de Teams est encore en cours d’exécution.  
- Si vous n’utilisez pas l’ordinateur sur lequel vous rencontrez ce problème, examinez le fichier `%LocalAppData%\SquirrelTemp\SquirrelSetup.log` collecté à partir de l’ordinateur qui rencontre ce problème et recherchez l’entrée **Programme : impossible de terminer le processus dans le journal**.
- Pour déterminer ce qui empêche la sortie de `Teams.exe`, regardez les journaux `Dlls.txt` et `Handles.txt` que vous avez créés dans la section [Collecter les journaux](#collect-logs). Ceux-ci indiquent les processus qui ont empêché Teams de quitter.
- Un autre coupable de pouvoir empêcher Teams de quitter est le pilote de filtre de système de fichiers en mode noyau. Utilisez l’outil SysInternals, [ProcDump](/sysinternals/downloads/procdump), pour collecter le vidage du processus en mode noyau en exécutant `procdump -mk <pid>`, où \<pid> est l’ID de processus obtenu à partir du Gestionnaire des tâches. Vous pouvez également inspecter le fichier journal `Driverquery.txt` pour afficher les pilotes de filtre actifs qui peuvent interférer avec Teams.
- Pour récupérer à partir de cet état, redémarrez l’ordinateur.

#### <a name="file-permissions"></a>Autorisations d’accès aux fichiers

Teams crée un certain nombre de sous-dossiers et de fichiers dans le profil de l’utilisateur tout au long du processus d’installation et de mise à jour. Étant donné que l’application et le programme de mise à jour sont exécutés en tant qu’utilisateurs non élevés, les autorisations de lecture et d’écriture doivent être accordées sur les dossiers suivants :

|Dossier  |Utilisateur  |
|---------|---------|
|`%LocalAppData%\SquirrelTemp`    | Programme d’installation de Teams (par exemple, `Teams_Windows_x64.exe`) lors de la phase d’installation        |
|`%LocalAppData%\Microsoft\Teams`  | Programme de mise à jour Teams (`Update.exe`) pour extraire et organiser le package d’application lors du processus de mise à jour        |
|`%AppData%\Microsoft\Teams`   |  Application Teams (`Teams.exe`) pour enregistrer les paramètres, les états de l’application et le package de mise à jour téléchargé (préinstallé)       |

Si l’accès à Teams est refusé parce qu’il ne peut pas écrire dans un fichier, il est possible qu’une autre application logicielle interfère ou qu’une entrée de descripteur de sécurité limite l’accès en écriture à un dossier.

Conseils de dépannage :

- Rechercher la preuve `access denied` dans `%LocalAppData%\SquirrelTemp\SquirrelSetup.log` ou `%AppData%\Microsoft\Teams\logs.txt`. Vérifiez ces fichiers pour voir s’il y a eu une tentative d’écriture dans un fichier qui a échoué.
- Ouvrez `Icacls.txt` et recherchez l’entrée de contrôle d’accès (ACE) effective qui bloque les opérations d’écriture d’un utilisateur qui n’est pas un administrateur. Il s’agit généralement de l’une des entrées DACL. Pour plus d’informations, voir la [documentation icacls](/windows-server/administration/windows-commands/icacls).

#### <a name="file-corrupted"></a>Fichier endommagé

Dans certains cas, les logiciels de chiffrement peuvent modifier les fichiers dans le dossier `%LocalAppData%\Microsoft\Teams`, ce qui peut empêcher Teams de démarrer. Cela peut se produire à tout moment, même si l’application n’est pas mise à jour. Lorsqu’un fichier est endommagé, la seule façon de récupérer cet état est de désinstaller et de réinstaller Teams.

> [!NOTE]
> Si vous ne parvenez pas à déterminer la cause sous-jacente du problème à l’aide de l’une de ces étapes, vous souhaiterez peut-être effectuer une session[Process monitor](/sysinternals/downloads/procmon). Process Monitor est un outil Sysinternals qui enregistre l’accès au registre et au système de fichiers.

## <a name="related-topics"></a>Voir aussi

- [Obtenir des clients pour Microsoft Teams](get-clients.md)
- [Mises à jour du client pour Teams](teams-client-update.md)
- [Résolution des problèmes de Teams](/MicrosoftTeams/troubleshoot/teams)
