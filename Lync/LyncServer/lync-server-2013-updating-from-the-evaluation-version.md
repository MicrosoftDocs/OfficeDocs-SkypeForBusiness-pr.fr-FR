---
title: Mise à jour à partir de la version d’évaluation de Lync Server 2013
TOCTitle: Mise à jour à partir de la version d’évaluation de Lync Server 2013
ms:assetid: 62a88180-4289-4a2a-9cb9-1b9899344a63
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg521005(v=OCS.15)
ms:contentKeyID: 49297404
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Mise à jour à partir de la version d’évaluation de Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-06-20_

Si vous avez installé la version d’évaluation de Microsoft Lync Server 2013, vous devrez mettre à jour cette installation avec une copie sous licence du logiciel ; ceci est dû au fait que la version d’évaluation expire 180 jours après sa date d’installation. Toutefois, vous ne devrez pas désinstaller complètement la version d’évaluation, puis installer la version sous licence. En effet, une fois que vous avez obtenu une clé de licence valide, vous pouvez mettre à jour la version d’évaluation de Lync Server 2013 en appliquant la procédure suivante sur chaque ordinateur qui est utilisé en tant que serveur frontalLync Server, directeur ou serveur Edge. Il n’est pas nécessaire de mettre à jour les ordinateurs ayant d’autres rôles serveur, tels qu’un serveur de surveillance ou un serveur d’archivage.

## Mise à jour à partir de la version d’évaluation de Microsoft Lync Server 2013

Pour mettre à jour un ordinateur depuis la version d’évaluation de Lync Server 2013 vers la version sous licence du logiciel :

**Mise à jour à partir de la version d’évaluation de Microsoft Lync Server 2013**

1.  Ouvrez une session sur l’ordinateur en tant qu’administrateur local.

2.  Cliquez sur **Démarrer**, sur **Tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Dans le Lync Server Management Shell, tapez la commande suivante, puis appuyez sur ENTRÉE :
    
        msiexec.exe /fvomus server.msi EVALTOFULL=1 /qb
    
    Il se peut que vous deviez spécifier le chemin d’accès complet au fichier server.msi. Ce fichier se trouve dans le dossier Setup des fichiers d’installation multimédias en volume Lync Server.

4.  Une fois l’installation terminée, tapez la commande suivante depuis l’invite de commande, puis appuyez sur ENTRÉE :
    
        Enable-CsComputer

5.  Répétez cette procédure sur tout autre serveur frontal, directeur ou serveur Edge exécutant une copie d’évaluation de Lync Server. Cette procédure doit aussi être réalisée sur tous les serveurs de succursale qui ont été déployés à l’aide des fichiers d’installation multimédias de Lync Server.

Si vous n’êtes pas certain que la version d’évaluation de Lync Server fonctionne sur un ordinateur particulier, vous pouvez le vérifier en exécutant la commande suivante depuis le Lync Server Management Shell :

    Get-CsServerVersion

L’applet de commande [Get-CsServerVersion](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsServerVersion) analyse l’ordinateur local et spécifie les éléments suivants :

  - La clé de licence en volume Lync Server a été installée sur l’ordinateur ; aucune mise à jour n’est donc nécessaire.

  - La clé de licence d’évaluation de Lync Server a été installée ; l’ordinateur doit donc être mis à jour.

  - Aucune clé de licence en volume n’est requise sur l’ordinateur. La mise à jour de la version d’évaluation vers la version sous licence est uniquement nécessaire sur les serveurs frontaux, les directeurs et les serveurs Edge.

