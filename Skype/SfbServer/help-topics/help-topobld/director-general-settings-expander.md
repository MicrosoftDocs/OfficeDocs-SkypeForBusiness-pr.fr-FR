---
title: Directeur général paramètres Expander
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.DirectorGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2026d0dd-6745-4e53-8b44-acdc378b47d1
description: 'Pour modifier les paramètres d’un directeur existant, les sections suivantes s’affiche :'
ms.openlocfilehash: e806f917dbcfe3e626410d3bb76caad3c40ed5d3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="director-general-settings-expander"></a>Directeur général paramètres Expander
 
Pour modifier les paramètres d’un directeur existant, les sections suivantes s’affiche :
  
- Paramètres généraux
    
- Services web
    
## 

### <a name="general-settings"></a>Paramètres généraux

Nom de domaine pleinement qualifié (FQDN) du pool directeur. Modifiez le nom de domaine complet du serveur pour changer la valeur. Vous devez disposer d’un enregistrement d’hôte DNS (A) correspondant à la nouvelle valeur.
  
Dans **Associations**, vous pouvez modifier ou spécifier les paramètres suivants :
  
Partage de fichiers pour le pool de directeur à utiliser. Sélectionnez un partage de fichiers existant qui a déjà été défini dans le Générateur de topologies, ou cliquez sur **Nouveau** pour créer une nouvelle définition de partage de fichier.
  
Surveillance de banque d’informations de SQL Server.
  
> [!IMPORTANT]
> Avant de publier la nouvelle topologie que vous venez de définir, le serveur que vous spécifiez doit exister et être joint au domaine. Si vous avez créé un nouveau partage de fichiers, le partage de fichiers doit être créé sur le serveur que vous désignez. 
  
### <a name="web-services"></a>Services web

Pour modifier ou spécifier des paramètres supplémentaires pour les services Web sur le pool de directeur, vous modifiez ou spécifiez des paramètres dans les services Web interne et les services Web externes.
  
Pour **interne de services web** , vous pouvez spécifier les éléments suivants :
  
> [!CAUTION]
> Si vous avez plus d’un pool frontal ou serveur frontal des services Web externes du nom de domaine complet doit être unique. Par exemple, si vous définissez les nom de domaine complet d’un serveur frontal des services Web externes comme **pool01.contoso.com**, vous ne pouvez pas utiliser **pool01.contoso.com** pour un autre pool frontal ou un serveur frontal. Si vous déployez également les directeurs, les externes FQDN défini pour n’importe quel directeur de services Web ou directeur pool doit être unique à partir de n’importe quel autre directeur ou directeur du pool ainsi qu’un pool frontal ou un serveur frontal. Si vous décidez de remplacer les services web interne avec un nom de domaine complet définis par l’utilisateur, chaque nom de domaine complet doit être unique à partir de n’importe quel autre pool frontal, directeur ou un directeur.
  
Si vous sélectionnez Remplacer nom de domaine complet, vous pouvez spécifier un autre nom de domaine complet pour l’identité de services Web interne sur le pool. Par défaut, le paramètre est le nom du pool en cours définie pour le pool de directeur.
  
Vous pouvez spécifier des ports d’écoute et publiées pour HTTP et HTTPS qui nécessite de votre déploiement. Le paramètre par défaut du port 80 pour HTTP et 443 pour HTTPS sont les paramètres les plus courants et n’avez généralement pas besoin être modifiés sauf si vous avez des besoins spécifiques à votre société et de la conception de l’infrastructure.
  
Pour les **services web externes**, vous pouvez spécifier les éléments suivants :
  
Vous pouvez définir le nom de domaine complet des services Web externes. Le nom de domaine complet spécifié ici sera généralement défini par les exigences de votre connexion externe, comme le proxy inverse.
  
Vous pouvez spécifier des ports d’écoute et publiées pour HTTP et HTTPS qui nécessite de votre déploiement. Les paramètres par défaut, le port 8080 pour le protocole HTTP et le port 4443 pour le protocole HTTPS, sont définis initialement. Vous pouvez modifier ces paramètres pour les ports d’écoute en fonction des exigences de votre proxy inverse et de votre réseau externe. Les ports publiés sont définis par défaut sur le port 80 pour le protocole HTTP et sur le port 443 pour le protocole HTTPS. Ces valeurs déterminent quels ports le pool de directeur ou de directeur server écoutera les demandes entrantes. En règle générale, ces n’avez pas besoin d’être modifié, sauf s’il existe des conflits de ports requis sur le pool. Internes et externes des ports publiés qui utilisent les mêmes valeurs de port sont attendus. Cela n’entraîne aucun conflit.
  

