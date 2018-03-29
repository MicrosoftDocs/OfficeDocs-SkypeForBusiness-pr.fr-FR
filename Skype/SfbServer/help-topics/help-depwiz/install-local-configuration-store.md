---
title: Installer le magasin de configurations local
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 4/13/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
description: Pour commencer l’installation d’un nouveau Skype pour serveur de rôle 2015 de serveur d’entreprise, vous devez d’abord installer le SQL Server local qui héberge la banque de configuration local. Le magasin de configuration local agit comme un réplica en lecture seule de la Skype pour la banque de gestion Central Server (CMS). Vous devez être connecté au serveur de sont en cours d’exécution l’étape d’installation Local Configuration magasin en tant qu’administrateur local sur l’ordinateur et l’appartenance à la RTCUniversalServerAdmins ou le groupe RTCUniversalGlobalReadOnlyGroup. Si vous effectuez l’installation sur un serveur Edge, vous n’avez pas besoin d’être membre du groupe RTCUniversalServerAdmins ou RTCUniversalGlobalReadOnlyGroup. Le document de définition du Générateur de topologies est lu à partir du document de définition exportée plutôt qu’à partir du magasin Central de gestion. Pour exporter le document de définition du Générateur de topologies et le rendre disponible pour les serveurs Edge, consultez la rubrique Exporter de votre topologie et copie il sur un support externe pour l’Installation de bord.
ms.openlocfilehash: adce98e053b6959c3513885fc53f1616df1c1125
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="install-local-configuration-store"></a>Installer le magasin de configurations local
 
Pour commencer l’installation d’un nouveau Skype pour serveur de rôle 2015 de serveur d’entreprise, vous devez d’abord installer le SQL Server local qui héberge la banque de configuration local. Le magasin de configuration local agit comme un réplica en lecture seule de la Skype pour la banque de gestion Central Server (CMS). Vous devez être connecté au serveur décrit à l’étape **Installer le magasin de configurations local** en tant qu’administrateur local de l’ordinateur ; en outre, vous devez être membre du groupe RTCUniversalServerAdmins ou RTCUniversalGlobalReadOnlyGroup. Si vous effectuez l’installation sur un serveur Edge, vous n’avez pas besoin d’être membre du groupe RTCUniversalServerAdmins ou RTCUniversalGlobalReadOnlyGroup. Le document de définition du Générateur de topologies est lu à partir du document de définition exportée plutôt qu’à partir du magasin Central de gestion. Pour exporter le document de définition du Générateur de topologies et le rendre disponible pour les serveurs Edge, reportez-vous à la rubrique[exportation de votre topologie et copie sur un support externe pour l’Installation de bord](http://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx).
  
Pour commencer l’installation :
  
1. Sur le Skype pour Business Server 2015, page, à côté **étape 1 : magasin de Configuration Local Installation**, cliquez sur **exécuter**.
    
2. Dans la page **Configuration du serveur local** assurez-vous que l’option **Récupérer automatiquement la configuration à partir du magasin central de gestion** est sélectionnée, puis cliquez sur **Suivant**.
    
3. Une fois l’installation terminée, cliquez sur **Terminer**.
    
> [!NOTE]
> L’installation de la locale de SQL Server peut prendre un certain temps. Vous ne verrez pas les mises à jour de progression dans l’écran Résumé d’installation pendant l’installation de SQL Server. Si vous voulez surveiller la progression de l’installation, utilisez le Gestionnaire des tâches pour surveiller le programme d’installation de SQL Server. 
  

