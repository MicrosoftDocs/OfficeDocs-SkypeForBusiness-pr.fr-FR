---
title: Expanseur des paramètres généraux du directeur
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.DirectorGeneralSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 2026d0dd-6745-4e53-8b44-acdc378b47d1
ROBOTS: NOINDEX, NOFOLLOW
description: 'Les sections suivantes vous permettent de modifier les paramètres d’un directeur existant :'
ms.openlocfilehash: 773f687baaa9ea4d416fb31d46d0e8afb0e409e3
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60778554"
---
# <a name="director-general-settings-expander"></a>Expandeur des paramètres généraux du directeur
 
Les sections suivantes vous permettent de modifier les paramètres d’un directeur existant :
  
- Paramètres généraux
    
- Services Web
    

## <a name="general-settings"></a>Paramètres généraux

Nom de domaine complet (FQDN) du pool directeur. Modifiez le nom de domaine complet du serveur pour changer la valeur. Vous devez disposer d’un enregistrement DNS A (hôte) qui corresponde à la nouvelle valeur.
  
Dans **Associations**, vous pouvez modifier ou spécifier les paramètres suivants :
  
Partage de fichiers utilisé par le pool directeur. Sélectionnez un partage de fichiers existant qui a déjà été défini dans le Générateur de topologie, ou cliquez sur **Nouveau** pour créer une définition de partage de fichiers.
  
Magasin SQL Server de surveillance
  
> [!IMPORTANT]
> Avant de publier la nouvelle topologie que vous venez de définir, le serveur que vous spécifiez doit exister et être joint au domaine. Si vous avez créé un nouveau partage de fichiers, le partage de fichiers doit être créé sur le serveur que vous désignez. 
  
## <a name="web-services"></a>Services Web

Pour modifier ou spécifier des paramètres supplémentaires pour les services web sur le pool directeur, vous modifiez ou spécifiez des paramètres dans les services web internes et externes.
  
Dans le cas des **Services web internes**, vous pouvez spécifier les éléments suivants :
  
> [!CAUTION]
> Si vous avez plusieurs serveurs frontaux ou serveurs frontaux, le FQDN des services Web externes doit être unique. Par exemple, si vous définissez le nom de groupe des services Web externes d’un serveur frontal en tant que **pool01.contoso.com,** vous ne pouvez pas utiliser **pool01.contoso.com** pour un autre pool frontal ou serveur frontal. Si vous déployez également des directeurs, le nom de groupe des services Web externes défini pour un directeur ou un pool directeur doit être unique à partir d’un autre directeur ou pool directeur, ainsi que de tout pool frontal ou serveur frontal. Si vous décidez de remplacer les services web internes par un FQDN auto-défini, chaque FQDN doit être unique à partir de n’importe quel autre pool frontal, directeur ou pool directeur.
  
Si vous sélectionnez Remplacer le nom de domaine complet, vous pouvez indiquer un nom de domaine complet différent pour l’identité des services web sur le pool. Par défaut, le paramètre est le nom de pool actuel comme défini pour le pool directeur.
  
Vous pouvez spécifier des ports d’écoute et publiés pour HTTP et HTTPS nécessaires à votre déploiement. Le paramètre par défaut du port 80 pour HTTP et du port 443 pour HTTPS sont les paramètres les plus courants et ne doivent généralement pas être modifiés, à moins que vous n’ayez des exigences particulières au sein de votre organisation et de votre infrastructure.
  
Dans le cas des **Services web externes**, vous pouvez spécifier les éléments suivants :
  
Vous pouvez définir le nom de domaine complet des services web externes. Le nom de domaine complet spécifié ici sera généralement défini par les exigences de votre connexion externe, comme le proxy inverse.
  
Vous pouvez spécifier des ports d’écoute et publiés pour HTTP et HTTPS nécessaires à votre déploiement. Les paramètres par défaut du port 8080 pour HTTP et du port 4443 pour HTTPS sont initialement définis. Vous pouvez modifier ces paramètres pour les ports d’écoute en fonction des exigences liées à votre proxy inverse et à votre réseau externe. Les ports publiés sont définis par défaut sur le port 80 pour HTTP et le port 443 pour HTTPS. Ces valeurs déterminent les ports que le pool directeur ou le serveur directeur vont écouter pour les demandes entrantes. Elles ne doivent généralement pas être modifiées, sauf en cas de conflit entre les exigences en matière de port sur le pool. Les ports publiés internes et externes doivent utiliser les mêmes valeurs de port et cela n’entraîne aucun conflit.
  

