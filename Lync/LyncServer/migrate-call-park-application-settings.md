---
title: Migration des paramètres d’application de parcage d’appel
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate Call Park application settings
ms:assetid: 23b192d2-93ec-42a8-b175-b6ed502a2c35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687993(v=OCS.15)
ms:contentKeyID: 49733583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee1afd2e53bd29571818b9194fe77d3d350386f1
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888763"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-call-park-application-settings"></a>Migration des paramètres d’application de parcage d’appel

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-19_

La migration de l’application de parc d’appels de Lync Server 2010 vers Lync Server 2013 inclut la mise en service du pool Lync Server 2013 avec n’importe quel morceau de musique personnalisé sur les fichiers qui ont été téléchargés dans Lync Server 2010, en restaurant les paramètres de niveau de service et en reciblant le stationnement des appels vers le pool Lync Server 2013. Si des fichiers personnalisés de musique en attente ont été configurés dans le pool Lync Server 2010, ces fichiers doivent être copiés vers le nouveau pool Lync Server 2013. Par ailleurs, il est recommandé de sauvegarder les fichiers de conservation de musique personnalisés de Lync Server 2010 vers une autre destination pour conserver une copie de sauvegarde distincte de tous les fichiers de mise en attente personnalisés qui ont été téléchargés pour le parc d’appels. Les fichiers de conservation de musique personnalisés pour l’application de parc d’appels sont stockés dans le magasin de fichiers du pool. Pour copier les fichiers audio à partir d’un magasin de fichiers du pool Lync Server 2010 dans un magasin de fichiers 2013 Server, utilisez la commande **xcopy** avec les paramètres suivants :

   ```console
    Xcopy <Source: Lync Server 2010 Pool CPS File Store Path> <Destination: Lync Server 2013 Pool CPS File Store Path>
   ```

   ```console
    Example usage:  Xcopy "<Lync Server 2010 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Lync Server 2013 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
   ```

Lorsque tous les fichiers audio personnalisés ont été copiés sur le magasin de fichiers 2013 Lync Server, les paramètres de l’application de parc d’appels du pool Lync Server 2013 doivent être configurés et les plages d’orbites du parc d’appels associées au pool Lync Server 2010 doivent être réaffectées à le pool Lync Server 2013.

Les paramètres de l’application de parc d’appels incluent le seuil de délai de capture, l’activation ou la désactivation de la musique en attente, le nombre maximal de tentatives de sélection d’appels et la demande d’expiration. Vous devez gérer les paramètres de l’application parc d’appels à l’aide de Lync Server Management Shell pour exécuter l’applet de demande **Set-CsCpsConfiguration** . Vous ne pouvez pas gérer les paramètres de l’application parc d’appels à l’aide du panneau de configuration de Lync Server.

**Reconfigurer les paramètres du service de parc d’appels**

1.  À partir du serveur frontal Lync Server 2013, ouvrez Lync Server Management Shell.

2.  Dans la ligne de commande, tapez ce qui suit :
    
    <div>
    

    > [!NOTE]  
    > Si les paramètres de l’application de parc d’appels Lync Server 2013 sont identiques à ceux de l’ancienne génération de Lync Server 2010, vous pouvez ignorer cette étape. Si les paramètres d’application de parc d’appels sont différents pour les environnements Lync Server 2013 et Lync Server 2010, utilisez l’applet de cmdlet ci-dessous en tant que modèle pour mettre à jour ces modifications.

    
    </div>
    ```powershell
        Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>"-CallPickupTimeoutThreshold"<LS2010 CPS TimeSpan>"-EnableMusicOnHold"<LS2010 CPS value>"-MaxCallPickupAttempts"<LS2010 CPS pickup attempts>"-OnTimeoutURI"<LS2010 CPS timeout URI>"```

Pour réattribuer toutes les plages d’orbites du parc d’appels du pool Lync Server 2010 au pool Lync Server 2013, vous pouvez utiliser le panneau de configuration de Lync Server ou Lync Server Management Shell.

**Réaffecter toutes les plages d’orbites du parc d’appels à l’aide du panneau de configuration de Lync Server**

1.  Ouvrez le Paneau de configuration Lync Server.

2.  Dans le volet gauche, sélectionnez **fonctions vocales**.

3.  Sélectionnez l’onglet **parc d’appels** .

4.  Pour chaque gamme de parking d’appel attribuée à un pool Lync Server 2010, modifiez le paramètre **de nom de domaine complet du serveur de destination** et sélectionnez le pool lync Server 2013 qui traitera les demandes de parc d’appels.

5.  Sélectionnez **valider** pour enregistrer les modifications.

**Réaffecter toutes les plages d’orbites du parc d’appels à l’aide de Lync Server Management Shell**

1.  Ouvrez Lync Server Management Shell.

2.  Dans la ligne de commande, tapez ce qui suit :
    ```powershell
    Get-CsCallParkOrbit
    ```
    
    Cette cmdlet recense toutes les plages d’orbites du parc d’appels du déploiement. Toutes les orbites du parc d’appels avec les paramètres **CallParkServiceId** et **CallParkServerFqdn** définis comme le pool Lync Server 2010 doivent être réaffectées.
    
    Pour réattribuer la plage de la fonction d’appel de l’équipe du parc du serveur 2010 au pool Lync Server 2013, sur la ligne de commande, tapez ce qui suit :
    
    ```powershell
    Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Lync Server 2013 Pool FQDN>"
    ```

Après avoir réaffecté toutes les plages d’orbite du parc d’appels au pool Lync Server 2013, le processus de migration de l’application de parc d’appels sera exécuté et le pool Lync Server 2013 traitera toutes les futures demandes de parc d’appels.

</div>

<span> </span>

</div>

</div>

</div>

