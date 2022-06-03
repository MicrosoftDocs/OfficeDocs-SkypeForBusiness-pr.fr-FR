---
title: Installer Skype Entreprise Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 71299b34-8783-4384-9949-0d3162c8a36e
description: 'Résumé : Découvrez comment préparer votre environnement pour une installation de Skype Entreprise Server.'
ms.openlocfilehash: 32003fc1c269a0bf1b59afc965099851b6406ed6
ms.sourcegitcommit: e99471689ff60f9ab1095bc075f8b4c5569c9634
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860585"
---
# <a name="install-skype-for-business-server"></a>Installer Skype Entreprise Server
 
**Résumé:** Découvrez comment préparer votre environnement pour une installation de Skype Entreprise Server.
  
Cet article vous guide tout au long d’un exemple d’installation de Skype Entreprise Server. Cet article ne tente pas de couvrir toutes les procédures dont vous avez besoin pour effectuer une installation complète Skype Entreprise Server. L’objectif est de fournir des exemples de procédures dans une topologie étroitement définie qui inclut des fonctionnalités de base de réunion et de partage.
  
## <a name="overview-of-the-install-process-for-skype-for-business-server"></a>Vue d’ensemble du processus d’installation pour Skype Entreprise Server

Une installation de Skype Entreprise Server comprend de nombreuses procédures différentes. Les procédures dont vous avez besoin pour que Skype Entreprise Server s’exécutent dans votre environnement dépendent des spécificités de votre environnement. Par exemple, si vous utilisez Windows Server pour DNS, vous tirerez parti de l’exemple de procédure d’ajout d’une entrée DNS. Si vous utilisez un autre système pour DNS, vous devez suivre les procédures pour votre système DNS particulier. Cela est vrai pour la plupart des procédures de cette section.
  
Skype Entreprise Server est disponible dans Édition Standard et Êdition Entreprise. La principale différence est que Édition Standard ne prend pas en charge les fonctionnalités de haute disponibilité incluses dans Êdition Entreprise. 
  
Skype Entreprise Server est un produit avancé, et le processus d’installation exact dépend beaucoup de vos circonstances spécifiques. Cette section vous guide tout au long des étapes générales d’installation du produit. Toutefois, chaque procédure peut être différente en fonction de votre environnement et de vos décisions de planification. Par exemple, pour les petites organisations, un seul serveur, exécutant Skype Entreprise Server Édition Standard peut être approprié, alors qu’une grande organisation multinationale peut avoir 50 serveurs dans des emplacements dans le monde entier dédiés au produit.
  
> [!NOTE]
> Pour en savoir plus sur les dernières mises à jour cumulatives, consultez [Mises à jour pour Skype Entreprise Server](https://support.microsoft.com/kb/3061064). Après avoir installé le correctif CU1, un administrateur doit exécuter l’applet de  `Update-CsAdminRole` commande. Cette applet de commande est nécessaire pour accéder aux nouvelles applets de commande GCP sur Remote PowerShell.
  
> [!IMPORTANT]
> Les procédures décrites dans cette section servent d’exemple à l’aide d’un ensemble précis d’exigences et supposent que des décisions spécifiques ont déjà été prises. Les procédures réelles que vous devez installer Skype Entreprise Server seront probablement très différentes. Utilisez les procédures de cette section comme exemple uniquement et non comme guide pas à pas pour l’installation de Skype Entreprise Server dans tous les environnements. 
  
La mise en route Skype Entreprise Server pour la première fois implique huit étapes principales. Vous devez comprendre que les exemples de procédures de cette section ne sont pas les seules procédures requises pour l’installation de Skype Entreprise Server. Les huit étapes suivantes sont simplement des exemples pour vous aider à mieux comprendre le processus global et à mettre en place un environnement de travail de base. Vous pouvez effectuer les étapes 1 à 5 dans n’importe quel ordre. Toutefois, vous devez effectuer les étapes 6, 7 et 8 dans l’ordre, et après les étapes 1 à 5, comme indiqué dans le diagramme. Les huit étapes sont les suivantes :
  
![Vue d’ensemble du processus d’installation.](../../media/b1a59b39-a7f0-4781-ac4d-2dfef7ca3700.png)
  
- [Installer les prérequis pour Skype Entreprise Server](install-prerequisites.md) : installez les prérequis sur tous les serveurs qui composent la topologie Skype Entreprise Server. Notez que les prérequis ne sont pas les mêmes pour tous les rôles. Par exemple, les serveurs qui fournissent le rôle frontal ont un ensemble de prérequis, et les serveurs qui fournissent un rôle d’administrateur ont un ensemble différent de prérequis. Pour plus d’informations, consultez la documentation sur la planification des prérequis.
    
- [Créez un partage de fichiers dans Skype Entreprise Server](create-a-file-share.md) : créez un partage de fichiers qui sera utilisé par les serveurs tout au long de la topologie Skype Entreprise Server.
    
- [Installez les outils d’administration dans Skype Entreprise Server](install-administrative-tools.md) : les outils d’administration incluent le Générateur de topologie et Panneau de configuration. Vous devez installer les outils d’administration sur au moins un serveur de la topologie ou une station de travail de gestion 64 bits exécutant une version de système d’exploitation Windows prise en charge pour Skype Entreprise Server.
    
- [Préparer Active Directory pour Skype Entreprise Server](prepare-active-directory.md) : Skype Entreprise Server travaille en étroite collaboration avec Active Directory. Vous devez préparer le domaine Active Directory pour qu’il fonctionne avec Skype Entreprise Server. Vous pouvez le faire via l’Assistant Déploiement, et ce n’est fait qu’une seule fois pour le domaine. Cela est dû au fait que le processus crée des groupes et modifie le domaine, et vous n’avez besoin de le faire qu’une seule fois.
    
- [Créer des enregistrements DNS pour Skype Entreprise Server](create-dns-records.md) : pour que Skype Entreprise Server fonctionne correctement, un certain nombre de paramètres DNS doivent être en place. C’est pour que les clients sachent comment accéder aux services et que les serveurs se connaissent. Ces paramètres ne doivent être effectués qu’une seule fois par déploiement, car une fois que vous avez affecté une entrée DNS, elles sont disponibles dans l’ensemble du domaine.
    
- [Créer et publier une topologie dans Skype Entreprise Server](create-and-publish-new-topology.md) : avant de pouvoir installer le système Skype Entreprise Server sur chacun des serveurs de la topologie, vous devez créer une topologie et la publier. Lorsque vous publiez une topologie, vous chargez les informations de topologie dans la base de données du Magasin central de gestion. S’il s’agit d’un pool Êdition Entreprise, vous créez la base de données du Magasin central de gestion la première fois que vous publiez une nouvelle topologie. Si c’est Édition Standard, vous devez exécuter le processus Préparer le premier serveur Édition Standard à partir de l’Assistant Déploiement avant de publier une topologie. Cela permet de préparer Édition Standard en installant une instance SQL Server Express Edition et en créant le magasin central de gestion.
    
- [Installez Skype Entreprise Server sur les serveurs de la topologie](install-skype-for-business-server.md) : une fois que la topologie est chargée dans le magasin de gestion central et qu’Active Directory sait quels serveurs effectueront les rôles, vous devez installer le système Skype Entreprise Server sur chacun des serveurs de la topologie.
    
- [Vérifiez la topologie dans Skype Entreprise Server](verify-the-topology.md) : une fois la topologie publiée et les composants système Skype Entreprise Server installés sur chacun des serveurs de la topologie, vous êtes prêt à vérifier que la topologie fonctionne comme prévu. Cela inclut la vérification que la configuration s’est propagée à tous les serveurs Active Directory afin que l’ensemble du domaine sache que Skype Entreprise est disponible dans le domaine.
    

