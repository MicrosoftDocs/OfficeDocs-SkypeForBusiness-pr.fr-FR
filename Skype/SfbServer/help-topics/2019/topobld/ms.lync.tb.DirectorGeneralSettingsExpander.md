---
title: Expanseur des paramètres généraux du directeur
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.DirectorGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2026d0dd-6745-4e53-8b44-acdc378b47d1
ROBOTS: NOINDEX, NOFOLLOW
description: 'Pour modifier les paramètres d’un directeur existant, vous permettent des sections suivantes :'
ms.openlocfilehash: 1c292ec694583994131c926094e11eb0a7303e93
ms.sourcegitcommit: 1f7299f535ec6b34f92301b4abc14d8922492eeb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21065306"
---
# <a name="director-general-settings-expander"></a>Expanseur des paramètres généraux du directeur
 
Pour modifier les paramètres d’un directeur existant, vous permettent des sections suivantes :
  
- Paramètres généraux
    
- Services web
    

## <a name="general-settings"></a>Paramètres généraux

Nom de domaine complet (FQDN) du pool directeur. Modifiez le nom de domaine complet du serveur pour changer la valeur. Vous devez disposer d’un enregistrement d’hôte DNS (A) correspondant à la nouvelle valeur.
  
Dans **Associations**, vous pouvez modifier ou spécifier les paramètres suivants :
  
Partage de fichiers pour le pool directeur à utiliser. Sélectionnez un partage de fichiers existant qui a déjà été défini dans le Générateur de topologie, ou cliquez sur **Nouveau** pour créer une nouvelle définition de partage de fichier.
  
Surveillance du magasin SQL Server.
  
> [!IMPORTANT]
> Avant de publier la nouvelle topologie que vous venez de définir, le serveur que vous spécifiez doit exister et être joint au domaine. Si vous avez créé un nouveau partage de fichiers, le partage de fichiers doit être créé sur le serveur que vous désignez. 
  
## <a name="web-services"></a>Services web

Pour modifier ou spécifier des paramètres supplémentaires pour les services Web sur le pool directeur, vous modifiez ou spécifiez des paramètres dans les services Web internes et les services Web externes.
  
**Interne des services web** vous pouvez spécifier les éléments suivants :
  
> [!CAUTION]
> Si vous avez plus d’un pool frontal ou serveur frontal des services Web externes nom de domaine complet doit être unique. Par exemple, si vous définissez les nom de domaine complet d’un serveur frontal des services Web externes comme **pool01.contoso.com**, vous ne pouvez pas utiliser **pool01.contoso.com** pour un autre pool frontal ou serveur frontal. Si vous déployez également les directeurs, nom de domaine complet défini pour n’importe quel directeur des services Web externe ou pool directeur doit être unique à partir de n’importe quelle autre directeur ou directeur du pool ainsi qu’un pool frontal ou un serveur frontal. Si vous décidez de remplacer les services web internes avec un nom de domaine complet automatiquement défini, chaque nom de domaine complet doit être unique à partir de n’importe quel autre pool frontal, directeur ou un pool directeur.
  
Si vous sélectionnez Remplacer le nom de domaine complet, vous pouvez spécifier un nom de domaine complet différent pour l’identité des services web internes sur le pool. Par défaut, le paramètre est le nom du pool actuel défini pour le pool directeur.
  
Vous pouvez spécifier les ports d’écoute et publiés pour HTTP et HTTPS exigés par votre déploiement. Le paramètre par défaut du port 80 pour HTTP et le port 443 pour le protocole HTTPS sont les paramètres les plus courants et généralement n’avez pas besoin d’être modifié, sauf si vous avez des exigences spécifiques au sein de votre organisation et la conception de l’infrastructure.
  
Pour les **services web externes**, vous pouvez spécifier les éléments suivants :
  
Vous pouvez définir le nom de domaine complet des services Web externes. Le nom de domaine complet spécifié ici sera généralement défini par les exigences de votre connexion externe, comme le proxy inverse.
  
Vous pouvez spécifier les ports d’écoute et publiés pour HTTP et HTTPS exigés par votre déploiement. Les paramètres par défaut, le port 8080 pour le protocole HTTP et le port 4443 pour le protocole HTTPS, sont définis initialement. Vous pouvez modifier ces paramètres pour les ports d’écoute en fonction des exigences de votre proxy inverse et de votre réseau externe. Les ports publiés sont définis par défaut sur le port 80 pour le protocole HTTP et sur le port 443 pour le protocole HTTPS. Ces valeurs déterminent quels ports d’écoute pour les demandes entrantes du pool directeur ou serveur directeur. En règle générale, il est inutile à modifier, sauf s’il existe des conflits de ports requis sur le pool. Ports publiés internes et externes qui utilisent les mêmes valeurs de port sont prévus. Cela n’entraîne aucun conflit.
  

