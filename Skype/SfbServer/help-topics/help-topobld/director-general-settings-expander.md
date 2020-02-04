---
title: Développeur des paramètres généraux du directeur
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.DirectorGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2026d0dd-6745-4e53-8b44-acdc378b47d1
description: 'Pour modifier les paramètres d’un réalisateur existant, vous avez accès aux sections suivantes :'
ms.openlocfilehash: e9260b3b5caa8b5f8d788927f8d54f405f236631
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41697499"
---
# <a name="director-general-settings-expander"></a>Développeur des paramètres généraux du directeur
 
Pour modifier les paramètres d’un réalisateur existant, vous avez accès aux sections suivantes :
  
- Paramètres généraux
    
- Services web
    


## <a name="general-settings"></a>Paramètres généraux

Nom de domaine complet (FQDN) du pool de directeurs. Modifiez le nom de domaine complet du serveur pour changer la valeur. Vous devez disposer d’un enregistrement d’hôte DNS (A) correspondant à la nouvelle valeur.
  
Dans **Associations**, vous pouvez modifier ou spécifier les paramètres suivants :
  
Partage de fichiers pour le pool de réalisateurs à utiliser. Sélectionnez un partage de fichiers existant déjà défini dans le générateur de topologie ou cliquez sur **nouveau** pour créer une nouvelle définition de partage de fichiers.
  
Surveiller SQL Server Store.
  
> [!IMPORTANT]
> Avant de publier la nouvelle topologie que vous venez de définir, le serveur que vous spécifiez doit exister et être joint au domaine. Si vous avez créé un nouveau partage de fichiers, le partage de fichiers doit être créé sur le serveur que vous spécifiez. 
  
## <a name="web-services"></a>Services web

Pour modifier ou spécifier des paramètres supplémentaires pour les services Web dans la liste des directeurs, vous pouvez modifier ou spécifier des paramètres dans les services Web internes et les services Web externes.
  
Pour les **services Web internes** , vous pouvez spécifier les éléments suivants :
  
> [!CAUTION]
> Si vous avez plusieurs pools front-end ou serveur frontal, le nom de domaine complet des services Web externes doit être unique. Par exemple, si vous définissez le nom de domaine complet des services Web externes d’un serveur frontal en tant que **pool01.contoso.com**, vous ne pouvez pas utiliser **pool01.contoso.com** pour un autre pool frontal ou serveur frontal. Si vous déployez également des directeurs, le nom de domaine complet des services Web externes défini pour n’importe quel directeur ou pool de réalisateur doit être unique à partir d’un autre directeur ou pool de directeurs, ainsi que sur n’importe quel pool frontal ou serveur frontal. Si vous décidez de remplacer les services Web internes par un nom de domaine complet autonome, chaque nom de domaine complet doit être unique à partir de n’importe quel autre pool frontal, directeur ou pool de directeurs.
  
Si vous sélectionnez Remplacer le nom de domaine complet, vous pouvez spécifier un nom de domaine complet différent pour l’identité des services web internes sur le pool. Par défaut, le paramètre est le nom du pool actuel tel qu’il est défini pour le pool de réalisateurs.
  
Vous pouvez spécifier des ports d’écoute et de publication pour HTTP et HTTPs requis par votre déploiement. Le paramètre par défaut du port 80 pour HTTP et du port 443 pour HTTPs est les paramètres les plus courants et ne doit généralement pas être modifié, sauf si vous avez des exigences spécifiques au sein de votre organisation et de votre structure d’infrastructure.
  
Pour les **services Web externes**, vous pouvez spécifier les éléments suivants :
  
Vous pouvez définir le nom de domaine complet des services Web externes. Le nom de domaine complet spécifié ici sera généralement défini par les exigences de votre connexion externe, comme le proxy inverse.
  
Vous pouvez spécifier des ports d’écoute et de publication pour HTTP et HTTPs requis par votre déploiement. Les paramètres par défaut, le port 8080 pour le protocole HTTP et le port 4443 pour le protocole HTTPS, sont définis initialement. Vous pouvez modifier ces paramètres pour les ports d’écoute en fonction des exigences de votre proxy inverse et de votre réseau externe. Les ports publiés sont définis par défaut sur le port 80 pour le protocole HTTP et sur le port 443 pour le protocole HTTPS. Ces valeurs déterminent quels ports le serveur du pool de directeurs ou le serveur directeur écoutera pour les demandes entrantes. En règle générale, celles-ci n’ont pas besoin d’être modifiées, sauf s’il y a des conflits de port requis sur le pool. Les ports publiés internes et externes utilisant les mêmes valeurs de port sont attendus. Cela n’entraîne aucun conflit.
  

