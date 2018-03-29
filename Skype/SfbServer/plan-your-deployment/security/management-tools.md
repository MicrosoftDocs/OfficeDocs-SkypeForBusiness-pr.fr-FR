---
title: Outils de gestion de Windows PowerShell et Skype Entreprise Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6a285f7c-0ef5-4cab-9976-d03be276e35d
description: 'Dans Skype pour Business Server 2015, les outils de gestion sont implémentés à l’aide de Windows PowerShell. Windows PowerShell inclut un environnement de ligne de commande et un langage de script complet des commandes spécifiques au produit. Skype pour outils Business Server 2015 qui sont implémentées à l’aide de Windows PowerShell sont les suivants :'
ms.openlocfilehash: 25631ce7acf59567b431d7eebdf190c4b63d7913
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="windows-powershell-and-skype-for-business-server-2015-management-tools"></a>Outils de gestion de Windows PowerShell et Skype Entreprise Server 2015
 
Dans Skype pour Business Server 2015, les outils de gestion sont implémentés à l’aide de Windows PowerShell. Windows PowerShell inclut un environnement de ligne de commande et un langage de script complet des commandes spécifiques au produit. Skype pour outils Business Server 2015 qui sont implémentées à l’aide de Windows PowerShell sont les suivants : 
  
- **Générateur de topologies**. Vous utilisez le Générateur de topologies pour créer, ajuster et publier votre topologie planifiée, puis il valide votre topologie avant de procéder à des installations de serveur. Lorsque vous installez Skype pour Business Server 2015 sur des serveurs individuels, les serveurs lisent les topologies dans le cadre du processus d’installation et le programme d’installation déploie le serveur comme indiqué dans la topologie. Après l’installation, les informations de configuration sont automatiquement répliquées sur tous les serveurs. Les composants peuvent être ajoutés à votre déploiement uniquement à l’aide du Générateur de topologies.
    
- **Skype pour Business Server Management Shell**. Vous pouvez utiliser Skype pour Business Server Management Shell pour la gestion complète de la ligne de commande de votre déploiement.
    
- **Skype pour le panneau de configuration de Business Server**. Vous pouvez utiliser le Skype pour l’interface utilisateur du Panneau de configuration de Business Server pour gérer les tâches les plus courantes dans votre déploiement.
    
Ces outils utilisent des applets de commande Windows PowerShell pour la gestion de votre déploiement, y compris près de 550 applets de commande spécifiques au produit. Les applets de commande de sécurité inclus dans Skype pour Business Server 2015 sont principalement utilisés pour gérer l’authentification et les droits et les autorisations. Une vaste gamme d’applets de commande est disponible pour gérer l’authentification, dont des applets de commande pour l’authentification de certificats et de codes confidentiels (PIN). En outre, un certain nombre d’applets de commande activer vous permet d’utiliser la nouvelle fonctionnalité de contrôle d’accès basée sur les rôles (RBAC) pour déléguer le contrôle administratif de Skype pour Business Server 2015. Pour plus d’informations sur le Skype pour les applets de commande de serveur de l’entreprise, consultez [Skype pour Business Server 2015 Management Shell](../../manage/management-shell.md).
  
Les fonctionnalités de sécurité de script pour Windows PowerShell sont spécifiquement conçues pour éviter certains problèmes de sécurité liés au script des technologies plus anciennes, y compris Microsoft Visual Basic Scripting Edition (VBScript). Les fonctionnalités de sécurité de Windows PowerShell sont destinées à créer un environnement dans lequel les utilisateurs ne peuvent pas facilement ou exécuter des scripts à votre insu. Par défaut, les fonctionnalités de sécurité de Windows PowerShell sont activées. Vous pouvez modifier l’état de ces fonctionnalités pour les adapter à vos besoins de script et à divers objectifs de sécurité. Cela ne veut pas dire que le shell empêche les utilisateurs d’exécuter des scripts. Mais plutôt, il est plus difficile, par défaut, pour les utilisateurs d’exécuter des scripts sans en avoir conscience. Pour plus d’informations, consultez [Sécurité de Script Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=213145).
  

