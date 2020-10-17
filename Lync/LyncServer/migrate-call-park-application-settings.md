---
title: Migration des paramètres d’application de parcage d’appel
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate Call Park application settings
ms:assetid: 23b192d2-93ec-42a8-b175-b6ed502a2c35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687993(v=OCS.15)
ms:contentKeyID: 49733583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f63b91c6a742310d14031bdadc28cbc6ca57e115
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503561"
---
# <a name="migrate-call-park-application-settings"></a>Migration des paramètres d’application de parcage d’appel

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-19_

La migration de l’application de parcage d’appel de Lync Server 2010 vers Lync Server 2013 inclut la mise en service du pool Lync Server 2013 avec des fichiers de mise en attente musicaux personnalisés qui ont été téléchargés dans Lync Server 2010, la restauration des paramètres de niveau de service et le reciblage de toutes les orbites de parcage d’appel vers le pool Lync Server 2013. Si des fichiers de mise en attente musicale personnalisés ont été configurés dans le pool Lync Server 2010, ces fichiers doivent être copiés dans le nouveau pool Lync Server 2013. De plus, il est recommandé de sauvegarder tous les fichiers de mise en attente musicale personnalisés de Lync Server 2010 vers une autre destination afin de conserver une copie de sauvegarde distincte des fichiers musicaux en attente personnalisés qui ont été téléchargés pour le parcage d’appel. Les fichiers d’attente musicale personnalisée de l’application de parcage d’appel sont stockés dans le magasin de fichiers du pool. Pour copier les fichiers audio à partir d’un magasin de fichiers de pool Lync Server 2010 vers un magasin de fichiers Lync Server 2013, utilisez la commande **xcopy** avec les paramètres suivants :

   ```console
    Xcopy <Source: Lync Server 2010 Pool CPS File Store Path> <Destination: Lync Server 2013 Pool CPS File Store Path>
   ```

   ```console
    Example usage:  Xcopy "<Lync Server 2010 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Lync Server 2013 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
   ```

Lorsque tous les fichiers audio personnalisés ont été copiés dans le magasin de fichiers Lync Server 2013, les paramètres d’application de parcage d’appel du pool Lync Server 2013 doivent être configurés et les plages d’orbites de parcage d’appel associées au pool Lync Server 2010 doivent être réattribuées au pool Lync Server 2013.

Les paramètres de l’application de parcage d’appel incluent le seuil du délai d’attente de prise d’appel, l’activation ou la désactivation de l’attente musicale, le nombre maximal de tentatives de prise d’appel et la demande de délai d’expiration. Vous devez gérer les paramètres d’application de parcage d’appel à l’aide de Lync Server Management Shell pour exécuter la cmdlet **Set-CsCpsConfiguration** . Vous ne pouvez pas gérer les paramètres d’application de parcage d’appel à l’aide du panneau de configuration Lync Server.

**Reconfigurer les paramètres de l’application de parcage d’appel**

1.  À partir du serveur frontal Lync Server 2013, ouvrez Lync Server Management Shell.

2.  Dans la ligne de commande, tapez le code suivant :
    
    <div>
    

    > [!NOTE]  
    > Si vos paramètres d’application de parcage d’appel Lync Server 2013 sont identiques aux paramètres de Lync Server 2010 hérités, vous pouvez ignorer cette étape. Si les paramètres d’application de parcage d’appel sont différents pour les environnements Lync Server 2013 et Lync Server 2010, utilisez l’applet de commande ci-dessous comme modèle pour mettre à jour ces modifications.

    
    </div>
    ```powershell
        Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>"-CallPickupTimeoutThreshold" <LS2010 CPS TimeSpan> "-EnableMusicOnHold" <LS2010 CPS value> "-valeur maxcallpickupattempts" <LS2010 CPS pickup attempts> "-OnTimeoutURI" <LS2010 CPS timeout URI> " ```

Pour réaffecter toutes les plages d’orbites de parcage d’appel du pool Lync Server 2010 au pool Lync Server 2013, vous pouvez utiliser le panneau de configuration Lync Server ou Lync Server Management Shell.

**Réaffecter toutes les plages d’orbites de parcage d’appel à l’aide du Panneau de configuration Lync Server**

1.  Ouvrez le Panneau de configuration Lync Server.

2.  Dans le volet gauche, sélectionnez **Fonctionnalités vocales**.

3.  Sélectionnez l’onglet **Parcage d’appel**.

4.  Pour chaque plage d’orbites de parcage d’appel attribuée à un pool Lync Server 2010, modifiez le paramètre **nom de domaine complet du serveur de destination** et sélectionnez le pool lync Server 2013 qui traitera les demandes de parcage d’appel.

5.  Sélectionnez **Valider** pour enregistrer les modifications.

**Réaffecter toutes les plages d’orbites de parcage d’appel à l’aide de Lync Server Management Shell**

1.  Ouvrez Lync Server Management Shell.

2.  Sur la ligne de commande, tapez la commande suivante :
    ```powershell
    Get-CsCallParkOrbit
    ```
    
    Cette applet de commande répertorie toutes les plages d’orbites de parcage d’appel dans le déploiement. Toutes les orbites de parcage d’appel dont les paramètres **CallParkServiceId** et **CallParkServerFqdn** sont définis en tant que pool Lync Server 2010 doivent être réaffectées.
    
    Pour réaffecter les plages d’orbites de parcage d’appel Lync Server 2010 au pool Lync Server 2013, dans la ligne de commande, tapez ce qui suit :
    
    ```powershell
    Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Lync Server 2013 Pool FQDN>"
    ```

Après avoir réaffecté toutes les plages d’orbites de parcage d’appel au pool Lync Server 2013, le processus de migration de l’application de parcage d’appel est terminé et le pool Lync Server 2013 gère toutes les futures demandes de parcage d’appel.

</div>

<span> </span>

</div>

</div>

</div>

