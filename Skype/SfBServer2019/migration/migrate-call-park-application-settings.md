---
title: Migration des paramètres d’application de parcage d’appel
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'La migration de l’application de parc d’appels inclut la mise en service du pool Skype entreprise Server 2019 avec n’importe quel fichier de musique personnalisé sur les fichiers qui ont été téléchargés dans l’installation héritée, en restaurant les paramètres de niveau de service et en reciblant toutes les orbites du parc d’appels sur le Pool 2019 de Skype entreprise Server. Si des fichiers personnalisés de musique en attente ont été configurés dans la liste, ces fichiers doivent être copiés dans le nouveau pool Skype entreprise Server 2019. Par ailleurs, il est recommandé de sauvegarder les fichiers de conservation de musique personnalisés de votre parc d’appels à partir d’une autre destination pour conserver une copie de sauvegarde distincte de tous les fichiers de conservation de la musique personnalisés qui ont été téléchargés pour le parc d’appels. Les fichiers de conservation de musique personnalisés pour l’application de parc d’appels sont stockés dans le magasin de fichiers du pool. Pour copier les fichiers audio à partir d’un magasin de fichiers de réserve dans un magasin de fichiers 2019 Skype entreprise Server, utilisez la commande xcopy avec les paramètres suivants :'
ms.openlocfilehash: b9e55bc76e718d499482fb21e029a0a74e8f207f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813582"
---
# <a name="migrate-call-park-application-settings"></a>Migration des paramètres d’application de parcage d’appel

La migration de l’application de parc d’appels inclut la mise en service du pool Skype entreprise Server 2019 avec des fichiers personnalisés de conservation de la musique qui ont été téléchargés dans l’installation héritée, en restaurant les paramètres de niveau de service et en reciblant tout le parc d’appels. au pool 2019 de Skype entreprise Server. Si des fichiers personnalisés de musique en attente ont été configurés dans la liste, ces fichiers doivent être copiés dans le nouveau pool Skype entreprise Server 2019. Par ailleurs, il est recommandé de sauvegarder les fichiers de mise en attente personnalisés de votre parc d’appels dans une autre destination pour conserver une copie de sauvegarde distincte de tous les fichiers de conservation de la musique personnalisés qui ont été téléchargés pour le parc d’appels. Les fichiers de conservation de musique personnalisés pour l’application de parc d’appels sont stockés dans le magasin de fichiers du pool. Pour copier les fichiers audio à partir d’un magasin de fichiers de réserve dans un magasin de fichiers 2019 Skype entreprise Server, utilisez la commande **xcopy** avec les paramètres suivants : 

```
Xcopy <Source: legacy Pool CPS File Store Path> <Destination: Skype for Business Server 2019 Pool CPS File Store Path>
```

```
Example usage:  Xcopy "<legacy File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Skype for Business Server 2019 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
```

Lorsque tous les fichiers audio personnalisés ont été copiés dans le magasin de fichiers 2019 Skype entreprise Server, les paramètres d’application de parc d’appels du pool 2019 du serveur Skype entreprise doivent être configurés et les plages d’orbites du parc d’appels associées au pool hérité. doit être réaffecté au pool 2019 de Skype entreprise Server.

Les paramètres de l’application de parc d’appels incluent le seuil de délai d’attente de capture, l’activation ou la désactivation de la musique en attente, le nombre maximal de tentatives de sélection d’appels et la demande d’expiration. Vous devez gérer les paramètres de l’application parc d’appels à l’aide de Skype entreprise Server Management Shell pour exécuter l’applet de demande **Set-CsCpsConfiguration** . Vous ne pouvez pas gérer les paramètres de l’application parc d’appels à l’aide du panneau de configuration Skype entreprise Server. 

## <a name="reconfigure-the-call-park-service-settings"></a>Reconfigurer les paramètres du service de parc d’appels

1. À partir du serveur frontal Skype entreprise Server 2019, ouvrez Skype entreprise Server Management Shell.

2. Dans la ligne de commande, tapez ce qui suit :

    > [!NOTE]
    > Si vos paramètres d’application de parc d’appels Skype entreprise Server 2019 sont identiques à ceux de l’anciennement, vous pouvez ignorer cette étape. Si les paramètres de l’application de parc d’appels diffèrent pour les environnements 2019 et hérités de Skype entreprise Server, utilisez l’applet de cmdlet ci-dessous en tant que modèle pour mettre à jour ces modifications. 

   ```PowerShell
   Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"
   ```

Pour réattribuer toutes les plages d’orbites du parc d’appels à la liste de ressources partagées Skype entreprise Server 2019, vous pouvez utiliser le panneau de configuration Skype entreprise Server ou Skype entreprise Server Management Shell. 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-control-panel"></a>Réaffecter toutes les plages d’orbites du parc d’appels à l’aide de Skype entreprise Server panneau de configuration

1. Ouvrez le panneau de configuration Skype entreprise Server.

2. Dans le volet gauche, sélectionnez **fonctions vocales**.

3. Sélectionnez l’onglet **parc d’appels** . 

4. Pour chaque gamme de parking d’appel attribuée à un pool hérité, modifiez le paramètre **de nom de domaine complet du serveur de destination** et sélectionnez le pool Skype entreprise Server 2019 qui traitera les demandes de parc d’appels. 

5. Sélectionnez **valider** pour enregistrer les modifications. 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-management-shell"></a>Réaffecter toutes les plages d’orbites du parc d’appels à l’aide de Skype entreprise Server Management Shell

1. Ouvrez Skype entreprise Server Management Shell.

2. Dans la ligne de commande, tapez ce qui suit :

   ```PowerShell
   Get-CsCallParkOrbit
   ```

    Cette cmdlet recense toutes les plages d’orbites du parc d’appels du déploiement. Toutes les orbites du parc d’appels avec les paramètres **CallParkServiceId** et **CallParkServerFqdn** définis comme le pool hérité doivent être réaffectées. 

    Pour réaffecter les plages d’orbites du parc d’appels à la liste de commande 2019 du serveur Skype entreprise, dans la ligne de commande, tapez les informations suivantes :

   ```PowerShell
   Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Skype for Business Server 2019 Pool FQDN>"
   ```

Après avoir réaffecté toutes les plages d’orbite du parc téléphonique au pool 2019 de Skype entreprise Server, le processus de migration de l’application de parc d’appels sera exécuté et le pool de 2019 du serveur Skype entreprise gérera toutes les futures demandes de parc d’appels.


