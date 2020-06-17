---
title: Migration des paramètres d’application de parcage d’appel
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'La migration de l’application de parcage d’appel inclut la mise en service du pool Skype entreprise Server 2019 avec des fichiers de conservation musicaux personnalisés qui ont été téléchargés dans l’installation héritée, la restauration des paramètres de niveau de service et le reciblage de toutes les orbites de parcage d’appel vers le pool de Skype entreprise Server 2019. Si des fichiers de mise en attente musicale personnalisés ont été configurés dans le pool, ces fichiers doivent être copiés dans le nouveau pool Skype entreprise Server 2019. De plus, il est recommandé de sauvegarder tous les fichiers de conservation de musique personnalisée du parcage d’appel de vers une autre destination pour conserver une copie de sauvegarde distincte des fichiers de mise en attente musicale personnalisés qui ont été téléchargés pour le parcage d’appel. Les fichiers d’attente musicale personnalisée de l’application de parcage d’appel sont stockés dans le magasin de fichiers du pool. Pour copier les fichiers audio d’un magasin de fichiers de pool vers un magasin de fichiers 2019 de Skype entreprise, utilisez la commande xcopy avec les paramètres suivants :'
ms.openlocfilehash: ded38ab600da4b277b1cdc83218833c26df081aa
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752816"
---
# <a name="migrate-call-park-application-settings"></a>Migration des paramètres d’application de parcage d’appel

La migration de l’application de parcage d’appel inclut la mise en service du pool Skype entreprise Server 2019 avec des fichiers de conservation de musique personnalisés qui ont été téléchargés dans l’installation héritée, la restauration des paramètres de niveau de service et le reciblage de toutes les orbites de parcage d’appel vers le pool de Skype entreprise Server 2019. Si des fichiers de mise en attente musicale personnalisés ont été configurés dans le pool, ces fichiers doivent être copiés dans le nouveau pool Skype entreprise Server 2019. De plus, il est recommandé de sauvegarder tous les fichiers d’attente de musique personnalisés de parcage d’appel vers une autre destination pour conserver une copie de sauvegarde distincte des fichiers de mise en attente musicale personnalisés qui ont été téléchargés pour le parcage d’appel. Les fichiers d’attente musicale personnalisée de l’application de parcage d’appel sont stockés dans le magasin de fichiers du pool. Pour copier les fichiers audio d’un magasin de fichiers de pool vers un magasin de fichiers 2019 de Skype entreprise, utilisez la commande **xcopy** avec les paramètres suivants : 

```console
Xcopy <Source: legacy Pool CPS File Store Path> <Destination: Skype for Business Server 2019 Pool CPS File Store Path>
```

```console
Example usage:  Xcopy "<legacy File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Skype for Business Server 2019 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
```

Lorsque tous les fichiers audio personnalisés ont été copiés dans le magasin de fichiers de Skype entreprise Server 2019, les paramètres d’application de parcage d’appel du pool de Skype entreprise Server 2019 doivent être configurés et les plages d’orbites de parcage d’appel associées au pool hérité doivent être réattribuées au pool de Skype entreprise Server 2019.

Les paramètres de l’application parcage d’appel incluent le seuil de délai d’expiration de la collecte, l’activation ou la désactivation de la conservation de la musique, le nombre maximal de tentatives de prise d’appel et la demande de délai d’attente. Vous devez gérer les paramètres d’application de parcage d’appel à l’aide de Skype entreprise Server Management Shell pour exécuter la cmdlet **Set-CsCpsConfiguration** . Vous ne pouvez pas gérer les paramètres de l’application parcage d’appel à l’aide du panneau de configuration de Skype entreprise Server. 

## <a name="reconfigure-the-call-park-service-settings"></a>Reconfigurer les paramètres de l’application de parcage d’appel

1. À partir du serveur frontal Skype entreprise Server 2019, ouvrez Skype entreprise Server Management Shell.

2. Dans la ligne de commande, tapez le code suivant :

    > [!NOTE]
    > Si vos paramètres d’application de parcage d’appel Skype entreprise Server 2019 sont identiques aux paramètres hérités, vous pouvez ignorer cette étape. Si les paramètres d’application de parcage d’appel sont différents pour Skype entreprise Server 2019 et les environnements hérités, utilisez l’applet de commande ci-dessous comme modèle pour mettre à jour ces modifications. 

   ```PowerShell
   Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"
   ```

Pour réaffecter toutes les plages d’orbites de parcage d’appel du pool hérité vers le pool Skype entreprise Server 2019, vous pouvez utiliser le panneau de configuration de Skype entreprise Server ou Skype entreprise Server Management Shell. 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-control-panel"></a>Réaffecter toutes les plages d’orbites de parcage d’appel à l’aide du panneau de configuration Skype entreprise Server

1. Ouvrez le panneau de configuration de Skype entreprise Server.

2. Dans le volet gauche, sélectionnez **Fonctionnalités vocales**.

3. Sélectionnez l’onglet **Parcage d’appel**. 

4. Pour chaque plage d’orbites de parcage d’appel affectée à un pool hérité, modifiez le paramètre **nom de domaine complet du serveur de destination** et sélectionnez le pool Skype entreprise Server 2019 qui traitera les demandes de parcage d’appel. 

5. Sélectionnez **Valider** pour enregistrer les modifications. 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-management-shell"></a>Réaffecter toutes les plages d’orbites de parcage d’appel à l’aide de Skype entreprise Server Management Shell

1. Ouvrez Skype entreprise Server Management Shell.

2. Sur la ligne de commande, tapez la commande suivante :

   ```PowerShell
   Get-CsCallParkOrbit
   ```

    Cette applet de commande répertorie toutes les plages d’orbites de parcage d’appel dans le déploiement. Toutes les orbites de parcage d’appel dont les paramètres **CallParkServiceId** et **CallParkServerFqdn** sont définis en tant que pool hérité doivent être réaffectées. 

    Pour réaffecter les plages d’orbites de parcage d’appel hérité au pool Skype entreprise Server 2019, dans la ligne de commande, tapez ce qui suit :

   ```PowerShell
   Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Skype for Business Server 2019 Pool FQDN>"
   ```

Après avoir réaffecté toutes les plages d’orbites de parcage d’appel au pool Skype entreprise Server 2019, le processus de migration de l’application de parcage d’appel est terminé et le pool de Skype entreprise Server 2019 gère toutes les futures demandes de parcage d’appel.


