---
title: Migration des paramètres d’application de parcage d’appel
TOCTitle: Migration des paramètres d’application de parcage d’appel
ms:assetid: 23b192d2-93ec-42a8-b175-b6ed502a2c35
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ687993(v=OCS.15)
ms:contentKeyID: 49891266
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migration des paramètres d’application de parcage d’appel

 

_**Dernière rubrique modifiée :** 2012-10-19_

Le transfert de l’application de parcage d’appel de Lync Server 2010 vers Lync Server 2013 inclut la mise en service du pool Lync Server 2013 avec tous les fichiers d’attente musicale personnalisée téléchargés dans Lync Server 2010, la restauration des paramètres de niveau de service et le reciblage de tous les numéros d’appels parqués vers le pool Lync Server 2013. Si les fichiers d’attente musicale personnalisée ont été configurés dans le pool Lync Server 2010, ils doivent être copiés dans le nouveau pool Lync Server 2013. De plus, nous vous recommandons de sauvegarder les fichiers d’attente musicale personnalisée de parcage d’appel provenant de Lync Server 2010 dans un autre emplacement afin de conserver une copie de sauvegarde distincte des éventuels fichiers d’attente musicale personnalisée ayant été téléchargés pour le parcage d’appel. Les fichiers d’attente musicale personnalisée de l’application de parcage d’appel sont stockés dans le magasin de fichiers du pool. Pour copier les fichiers audio provenant d’un magasin de fichiers du pool Lync Server 2010 dans un magasin de fichiers Lync Server 2013, utilisez la commande **Xcopy** avec les paramètres suivants :

```
Xcopy <Source: Lync Server 2010 Pool CPS File Store Path> <Destination: Lync Server 2013 Pool CPS File Store Path>
```
```
Example usage:  Xcopy "<Lync Server 2010 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Lync Server 2013 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
```

Quand tous les fichiers audio personnalisés ont été copiés dans le magasin de fichiers Lync Server 2013, les paramètres de parcage d’appel du pool Lync Server 2013 doivent être configurés et les plages d’orbites du parcage d’appel associées au pool Lync Server 2010 doivent être réattribuées au pool Lync Server 2013.

Les paramètres de l’application de parcage d’appel incluent le seuil du délai d’attente de prise d’appel, l’activation ou la désactivation de l’attente musicale, le nombre maximal de tentatives de prise d’appel et la demande de délai d’expiration. Vous devez gérer les paramètres de l’application de parcage d’appel en utilisant Lync Server Management Shell pour exécuter l’applet de commande **Set-CsCpsConfiguration**. Vous ne pouvez pas gérer ces paramètres à l’aide du Panneau de configuration Lync Server.

**Reconfigurer les paramètres de l’application de parcage d’appel**

1.  Dans le serveur frontal Lync Server 2013, ouvrez Lync Server Management Shell.

2.  Dans la ligne de commande, tapez ce qui suit :
    
    > [!NOTE]  
    > Si les paramètres de votre application de parcage d’appel Lync Server 2013 sont identiques aux paramètres Lync Server 2010 hérités, vous pouvez ignorer cette étape. Si les paramètres de l’application de parcage d’appel sont différents pour les environnements Lync Server 2013 et Lync Server 2010, utilisez l’applet de commande ci-dessous comme modèle pour effectuer une mise à jour afin d’appliquer ces changements.    

    ```    
    Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"
    ```

Pour réaffecter toutes les plages d’orbites de parcage d’appel du pool Lync Server 2010 au pool Lync Server 2013, vous pouvez utiliser le Panneau de configuration Lync Server ou Lync Server Management Shell.

**Réaffecter toutes les plages d’orbites de parcage d’appel à l’aide du Panneau de configuration Lync Server**

1.  Ouvrez le Panneau de configuration Lync Server.

2.  Dans le volet gauche, sélectionnez **Fonctionnalités vocales**.

3.  Sélectionnez l’onglet **Parcage d’appel**.

4.  Pour chaque plage d’orbites de parcage d’appel attribuées à un pool Lync Server 2010, modifiez le paramètre **Nom de domaine complet du serveur de destination** et sélectionnez le pool Lync Server 2013 qui traitera les demandes de parcage d’appel.

5.  Sélectionnez **Valider** pour enregistrer les modifications.

**Réaffecter toutes les plages d’orbites de parcage d’appel à l’aide de Lync Server Management Shell**

1.  Ouvrez le Lync Server Management Shell.

2.  Dans la ligne de commande, tapez ce qui suit :
    
        Get-CsCallParkOrbit
    
    Cette applet de commande répertorie toutes les plages d’orbites de parcage d’appel dans le déploiement. Toutes les orbites de parcage d’appel dont les paramètres **CallParkServiceId** et **CallParkServerFqdn** sont définis comme étant le pool Lync Server 2010 doivent être réaffectées.
    
    Pour réaffecter les plages d’orbites de parcage d’appel Lync Server 2010 au pool Lync Server 2013, dans la ligne de commande, tapez la commande suivante :
    
        Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Lync Server 2013 Pool FQDN>"

Une fois toutes les plages d’orbites de parcage d’appel réaffectées au pool Lync Server 2013, le processus de transfert de l’application de parcage d’appel sera effectué et le pool Lync Server 2013 traitera toutes les futures demandes de parcage d’appel.

