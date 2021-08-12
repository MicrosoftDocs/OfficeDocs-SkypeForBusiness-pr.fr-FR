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
description: 'La migration de l’application de parcage d’appel inclut la mise en service du pool Skype Entreprise Server 2019 avec tous les fichiers d’attente musicale personnalisés qui ont été téléchargés dans l’installation héritée, la restauration des paramètres de niveau de service et le retargeting de toutes les orbites de parcage d’appel vers le pool Skype Entreprise Server 2019. Si des fichiers d’attente musicale personnalisés ont été configurés dans le pool, ces fichiers doivent être copiés dans le nouveau pool Skype Entreprise Server 2019. En outre, il est recommandé de sauvegarder tous les fichiers d’attente musicale personnalisés du parcement d’appel à partir d’une autre destination afin de conserver une copie de sauvegarde distincte des fichiers d’attente musicale personnalisés qui ont été téléchargés pour le parcement d’appel. Les fichiers d’attente musicale personnalisée de l’application de parcage d’appel sont stockés dans le magasin de fichiers du pool. Pour copier les fichiers audio d’un magasin de fichiers de pool vers un magasin de fichiers Skype Entreprise Server 2019, utilisez la commande Xcopy avec les paramètres suivants :'
ms.openlocfilehash: f83e1095361ddd272a35bf9100171c0d06caf003dfae84f19c01b2aa53de7977
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54312322"
---
# <a name="migrate-call-park-application-settings"></a>Migration des paramètres d’application de parcage d’appel

La migration de l’application de parcage d’appel inclut la mise en service du pool Skype Entreprise Server 2019 avec tous les fichiers d’attente musicale personnalisés qui ont été téléchargés dans l’installation héritée, la restauration des paramètres au niveau du service et le ciblage de toutes les orbites de parcage d’appel vers le pool Skype Entreprise Server 2019. Si des fichiers d’attente musicale personnalisés ont été configurés dans le pool, ces fichiers doivent être copiés dans le nouveau pool Skype Entreprise Server 2019. En outre, il est recommandé de sauvegarder tous les fichiers d’attente musicale personnalisés du parcement d’appel vers une autre destination pour conserver une copie de sauvegarde distincte des fichiers d’attente musicale personnalisés qui ont été téléchargés pour le parcement d’appel. Les fichiers d’attente musicale personnalisée de l’application de parcage d’appel sont stockés dans le magasin de fichiers du pool. Pour copier les fichiers audio d’un magasin de fichiers de pool vers un magasin de fichiers Skype Entreprise Server 2019, utilisez la commande **Xcopy** avec les paramètres suivants : 

```console
Xcopy <Source: legacy Pool CPS File Store Path> <Destination: Skype for Business Server 2019 Pool CPS File Store Path>
```

```console
Example usage:  Xcopy "<legacy File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Skype for Business Server 2019 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
```

Lorsque tous les fichiers audio personnalisés ont été copiés dans le magasin de fichiers Skype Entreprise Server 2019, les paramètres d’application de parcage d’appel du pool Skype Entreprise Server 2019 doivent être configurés et les plages d’orbites de parcage d’appel associées au pool hérité doivent être réassignées au pool Skype Entreprise Server 2019.

Les paramètres de l’application de parcage d’appel incluent le seuil de délai d’attente de prise d’appel, l’activation ou la désactivation de l’attente musicale, le nombre maximal de tentatives de prise d’appel et la demande de délai d’attente. Vous devez gérer les paramètres de l’application de parcage d’appel à l’aide de Skype Entreprise Server Management Shell pour exécuter l’cmdlet **Set-CsCpsConfiguration.** Vous ne pouvez pas gérer les paramètres de l’application de parcage d’appel à l’aide Skype Entreprise Server panneau de configuration. 

## <a name="reconfigure-the-call-park-service-settings"></a>Reconfigurer les paramètres de l’application de parcage d’appel

1. À partir Skype Entreprise Server serveur frontal 2019, ouvrez Skype Entreprise Server Management Shell.

2. Dans la ligne de commande, tapez le code suivant :

    > [!NOTE]
    > Si vos paramètres Skype Entreprise Server d’application de parcage d’appel 2019 sont identiques aux paramètres hérités, vous pouvez ignorer cette étape. Si les paramètres de l’application de parcage d’appel sont différents pour les environnements Skype Entreprise Server 2019 et hérités, utilisez la cmdlet ci-dessous comme modèle pour mettre à jour ces modifications. 

   ```PowerShell
   Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"
   ```

Pour réaffecter toutes les plages d’orbites de parcage d’appel du pool hérité au pool Skype Entreprise Server 2019, vous pouvez utiliser le Panneau de Skype Entreprise Server ou l’Skype Entreprise Server Management Shell. 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-control-panel"></a>Réaffecter toutes les plages d’orbites de parc Skype Entreprise Server panneau de commande

1. Ouvrez Skype Entreprise Server panneau de contrôle.

2. Dans le volet gauche, sélectionnez **Fonctionnalités vocales**.

3. Sélectionnez l’onglet **Parcage d’appel**. 

4. Pour chaque plage d’orbites de parcage d’appel affectée à un pool hérité, modifiez le nom de groupe du paramètre du serveur de **destination** et sélectionnez le pool Skype Entreprise Server 2019 qui traitera les demandes de parcage d’appel. 

5. Sélectionnez **Valider** pour enregistrer les modifications. 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-management-shell"></a>Réaffecter toutes les plages d’orbites de parc Skype Entreprise Server Management Shell

1. Ouvrez Skype Entreprise Server Management Shell.

2. Sur la ligne de commande, tapez la commande suivante :

   ```PowerShell
   Get-CsCallParkOrbit
   ```

    Cette applet de commande répertorie toutes les plages d’orbites de parcage d’appel dans le déploiement. Toutes les orbites de parcage d’appel dont les paramètres **CallParkServiceId** et **CallParkServerFqdn** sont définies comme pool hérité doivent être réassignés. 

    Pour réaffecter les plages d’orbites de parcage d’appel héritées au pool Skype Entreprise Server 2019, sur la ligne de commande, tapez ce qui suit :

   ```PowerShell
   Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Skype for Business Server 2019 Pool FQDN>"
   ```

Après avoir réaffecté toutes les plages d’orbites de parcage d’appel au pool Skype Entreprise Server 2019, le processus de migration de l’application de parcage d’appel sera terminé et le pool Skype Entreprise Server 2019 gérera toutes les futures demandes de parcage d’appel.


