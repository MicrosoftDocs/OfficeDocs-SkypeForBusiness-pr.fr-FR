---
title: Installation de Skype Entreprise Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 7/14/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 71299b34-8783-4384-9949-0d3162c8a36e
description: 'Résumé : Découvrez comment préparer votre environnement pour une installation de Skype pour Business Server. Téléchargez une version d’évaluation gratuite de Skype pour Business Server depuis le centre d’évaluation Microsoft à : https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: 041c60c23e5edc56a0332f7e0321fd1aac5970f8
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898521"
---
# <a name="install-skype-for-business-server"></a>Installation de Skype Entreprise Server
 
**Résumé :** Découvrez comment préparer votre environnement pour une installation de Skype pour Business Server. Téléchargez une version d’évaluation gratuite de Skype pour Business Server depuis le centre d’évaluation Microsoft à :[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Cet article vous guide dans une installation de l’exemple de Skype pour Business Server. Cet article n’essaie pas de couvrir toutes les procédures que vous devez effectuer une Skype complète pour l’installation du serveur d’entreprise. Son but est de fournir des exemples de procédures dans une topologie étroitement définie, qui comprend les fonctionnalités standard de réunion et de partage.
  
## <a name="overview-of-the-install-process-for-skype-for-business-server"></a>Vue d’ensemble du processus d’installation pour Skype pour Business Server

Une installation de Skype pour Business Server inclut de nombreuses différentes procédures. Les procédures que vous devez obtenir Skype pour Business Server en cours d’exécution dans votre environnement dépendant des caractéristiques de votre environnement. Par exemple, si vous utilisez Windows Server pour le DNS, vous pourrez tirer parti de l’exemple de procédure pour l’ajout d’une entrée DNS. Si vous utilisez un autre système pour le DNS, vous devez suivre les procédures de votre système DNS particulier. Ceci est vrai pour de nombreuses procédures de cette section.
  
Skype pour Business Server est disponible dans Standard Edition et Enterprise Edition. La principale différence est que Standard Edition ne prend pas en charge les fonctionnalités de haute disponibilité qui sont incluses avec Enterprise Edition. 
  
Skype pour Business Server est un produit, et le processus d’installation exacte dépend beaucoup de circonstances spécifiques. Cette section vous présente les étapes générales pour installer le produit. Toutefois, chaque procédure peut être différente en fonction de votre environnement et les décisions de planification. Par exemple, pour les petites organisations un serveur unique, en cours d’exécution Skype pour Business Server Standard Edition convient, tandis que d’une grande entreprise multinationale peut-être 50 serveurs au niveau du monde dédiée pour le produit.
  
> [!NOTE]
> Pour en savoir plus sur les dernières mises à jour cumulatives, voir [mises à jour pour Skype pour Business Server](https://support.microsoft.com/en-us/kb/3061064). Après avoir installé le correctif CU1 un administrateur doit exécuter le `Update-CsAdminRole` applet de commande. Cette applet de commande est requise pour les nouvelles applets de commande GCP d’accéder via PowerShell à distance.
  
> [!IMPORTANT]
> Les procédures de cette section sont destinées à servir d’exemple en utilisant un ensemble étroitement défini d’exigences et en supposant que des décisions spécifiques ont déjà été prises. Les procédures que vous devez installer Skype pour Business Server sera probablement très différentes. Utilisez les procédures de cette section en guise d’exemple uniquement et non comme un guide pas à pas pour l’installation de Skype pour Business Server dans chaque environnement. 
  
Huit étapes essentielles impliquent la route Skype pour Business Server et en cours d’exécution pour la première fois. Vous devez comprendre les exemples de procédures de cette section ne sont pas les seules procédures requises pour l’installation Skype pour Business Server. Les huit étapes suivantes sont simplement des exemples permettant de mieux comprendre l’ensemble du processus et d’obtenir un environnement de travail de base opérationnel. Vous pouvez effectuer les étapes 1 à 5 dans un ordre quelconque. Cependant, vous devez exécuter les étapes 6, 7 et 8 dans l’ordre et après les étapes 1 à 5 comme indiqué dans le diagramme. Les huit étapes sont les suivantes :
  
![Vue d’ensemble de la procédure d’installation.](../../media/b1a59b39-a7f0-4781-ac4d-2dfef7ca3700.png)
  
- [Installer les composants requis pour Skype pour Business Server](install-prerequisites.md) : installer les composants requis sur tous les serveurs qui constituent le Skype pour la topologie du serveur d’entreprise. Notez que les prérequis ne sont pas les mêmes pour tous les rôles. Par exemple, les serveurs qui fourniront le rôle frontal présentent un ensemble de prérequis et les serveurs qui fourniront un rôle de Directeur présentent un autre ensemble de prérequis. Consultez la documentation de planification des prérequis pour plus de détails.
    
- [Créer un partage de fichiers dans Skype pour Business Server](create-a-file-share.md) : créer un partage de fichiers qui sera utilisé par les serveurs de la Skype pour la topologie du serveur d’entreprise.
    
- [Installer les outils d’administration dans Skype pour Business Server](install-administrative-tools.md) : les outils d’administration incluent le Générateur de topologie et le panneau de configuration. Vous devez installer les outils d’administration sur au moins un serveur dans la topologie ou une station de travail de gestion 64 bits qui exécute une version du système d’exploitation Windows pris en charge pour Skype pour Business Server.
    
- [Préparer Active Directory pour Skype pour Business Server](prepare-active-directory.md) : Skype pour Business Server travaille en étroite collaboration avec Active Directory. Vous devez préparer le domaine Active Directory pour fonctionner avec Skype pour Business Server. Vous pouvez effectuer ce processus dans l’assistant Déploiement, et ce processus n’est effectué qu’une seule fois pour le domaine. Ceci est dû au fait que le processus crée des groupes et modifie le domaine et vous n’avez besoin d’effectuer cette opération qu’une seule fois.
    
- [Créer des enregistrements DNS pour Skype pour Business Server](create-dns-records.md) : afin que Skype pour Business Server fonctionne correctement, un nombre de paramètres DNS doit être en place. Ceci afin que les clients sachent comment accéder aux services et que les serveurs se connaissent entre eux. Ces paramètres ne doivent être définis qu’une seule fois par déploiement, car, dans la mesure où vous attribuez une entrée DNS, elle est disponible dans tout le domaine.
    
- [Créer et publier la nouvelle topologie dans Skype pour Business Server](create-and-publish-new-topology.md) : avant de pouvoir installer le Skype pour système Business Server sur chacun des serveurs de la topologie, vous devez créer une topologie et le publier. Lorsque vous publiez une topologie, vous chargez les informations dans la base de données du magasin central de gestion. S’il s’agit d’un pool Enterprise Edition, vous créez la base de données du magasin central de gestion la première fois que vous publiez une nouvelle topologie. S’il s’agit de Standard Edition, vous devez exécuter le processus de préparer le premier serveur Standard Edition Server à partir de l’Assistant déploiement avant de publier une topologie. Il prépare l’installation de Standard Edition en installant une instance de SQL Server Express Edition et en créant le magasin central de gestion.
    
- [Installer les Skype pour Business Server sur les serveurs de la topologie](install-skype-for-business-server.md) : une fois la topologie est chargée dans le magasin Central de gestion et Active Directory ne connaît les serveurs qui exécutera les rôles, vous devez installer le Skype pour système Business Server sur chaque serveur de les serveurs de la topologie.
    
- [Vérifier la topologie dans Skype pour Business Server](verify-the-topology.md) : une fois que la topologie publiée et la Skype pour les composants du système Business Server installé sur chacun des serveurs dans la topologie, vous êtes prêt à vérifier que la topologie fonctionne comme prévu. Cela inclut de vérifier que la configuration s’est propagée à tous les serveurs Active Directory pour que la totalité du domaine sache que Skype pour les entreprises est disponible dans le domaine.
    

