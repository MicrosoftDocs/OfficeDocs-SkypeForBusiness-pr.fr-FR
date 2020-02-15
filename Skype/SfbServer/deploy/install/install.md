---
title: Installer Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 71299b34-8783-4384-9949-0d3162c8a36e
description: 'Résumé : Découvrez comment préparer votre environnement pour une installation de Skype entreprise Server. Téléchargez une version d’évaluation gratuite de Skype entreprise Server à partir du centre d’évaluation https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverMicrosoft à l’adresse suivante :.'
ms.openlocfilehash: e33e773abf25be92c163de259af0c3f47e0b1783
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042381"
---
# <a name="install-skype-for-business-server"></a>Installer Skype entreprise Server
 
**Résumé :** Découvrez comment préparer votre environnement pour une installation de Skype entreprise Server. Téléchargez une version d’évaluation gratuite de Skype entreprise Server à partir du centre d’évaluation[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)Microsoft à l’adresse suivante :.
  
Cet article vous guide dans un exemple d’installation de Skype entreprise Server. Cet article ne tente pas de traiter toutes les procédures dont vous avez besoin pour effectuer une installation complète de Skype entreprise Server. L’objectif est de fournir des exemples de procédures dans une topologie étroitement définie qui inclut la fonctionnalité de réunion et de partage de base.
  
## <a name="overview-of-the-install-process-for-skype-for-business-server"></a>Vue d’ensemble du processus d’installation de Skype entreprise Server

Une installation de Skype entreprise Server comprend de nombreuses procédures différentes. Les procédures nécessaires pour que Skype entreprise Server s’exécute dans votre environnement dépendent des spécificités de votre environnement. Par exemple, si vous utilisez Windows Server pour DNS, vous bénéficierez de l’exemple de procédure d’ajout d’une entrée DNS. Si vous utilisez un autre système pour DNS, vous devez suivre les procédures pour votre système DNS particulier. Ceci est vrai pour de nombreuses procédures de cette section.
  
Skype entreprise Server est disponible dans Standard Edition et Enterprise Edition. La principale différence réside dans le fait que Standard Edition ne prend pas en charge les fonctionnalités de haute disponibilité incluses dans Enterprise Edition. 
  
Skype entreprise Server est un produit avancé, et le processus d’installation exact dépend d’un grand rapport avec vos circonstances spécifiques. Cette section décrit les étapes générales d’installation du produit. Toutefois, chaque procédure peut varier en fonction de votre environnement et des décisions de planification. Par exemple, pour les petites organisations, un serveur unique, qui exécute Skype entreprise Server Standard Edition peut être approprié, tandis qu’une grande organisation multinationale peut avoir 50 serveurs à des emplacements différents du monde entier dédié au produit.
  
> [!NOTE]
> Pour en savoir plus sur les dernières mises à jour cumulatives, consultez la rubrique [mises à jour pour Skype entreprise Server](https://support.microsoft.com/kb/3061064). Après avoir installé le correctif CU1, un administrateur doit exécuter `Update-CsAdminRole` l’applet de commande. Cette applet de commande est requise pour accéder aux nouvelles applets de commande GCP via PowerShell à distance.
  
> [!IMPORTANT]
> Les procédures décrites dans cette section constituent un exemple d’utilisation d’un ensemble d’exigences défini de manière étroite et qui supposent que des décisions spécifiques ont déjà été prises. Les procédures réelles requises pour installer Skype entreprise Server seront probablement très différentes. Utilisez les procédures de cette section à titre d’exemple uniquement et pas en tant que guide pas à pas pour l’installation de Skype entreprise Server dans chaque environnement. 
  
L’installation de Skype entreprise Server pour la première fois implique huit étapes principales. Vous devez comprendre que les procédures présentées dans cette section ne sont pas les seules procédures requises pour l’installation de Skype entreprise Server. Les huit étapes suivantes sont simplement des exemples pour vous aider à mieux comprendre le processus global et à faire fonctionner un environnement de travail de base. Vous pouvez effectuer les étapes 1 à 5 dans n’importe quel ordre. Toutefois, vous devez effectuer les étapes 6, 7 et 8 dans l’ordre et après les étapes 1 à 5, comme indiqué dans le diagramme. Les huit étapes sont les suivantes :
  
![Vue d’ensemble du processus d’installation.](../../media/b1a59b39-a7f0-4781-ac4d-2dfef7ca3700.png)
  
- [Installer les composants requis pour Skype entreprise Server](install-prerequisites.md) : Installez les composants requis sur tous les serveurs qui composent la topologie Skype entreprise Server. Notez que les conditions préalables ne sont pas les mêmes pour tous les rôles. Par exemple, les serveurs qui fournissent le rôle frontal disposent d’un ensemble de conditions préalables, et les serveurs qui fournissent un rôle directeur ont un ensemble de conditions préalables différent. Pour plus d’informations, reportez-vous à la documentation de planification requise.
    
- [Créer un partage de fichiers dans Skype entreprise Server](create-a-file-share.md) : créez un partage de fichiers qui sera utilisé par les serveurs dans la topologie Skype entreprise Server.
    
- [Installer les outils d’administration dans Skype entreprise Server](install-administrative-tools.md) : les outils d’administration comprennent le générateur de topologie et le panneau de configuration. Vous devez installer les outils d’administration sur au moins un serveur de la topologie ou sur une station de travail de gestion 64 bits exécutant une version du système d’exploitation Windows prise en charge pour Skype entreprise Server.
    
- [Préparer Active Directory pour Skype entreprise Server](prepare-active-directory.md) : Skype entreprise Server fonctionne en étroite collaboration avec Active Directory. Vous devez préparer le domaine Active Directory pour qu’il fonctionne avec Skype entreprise Server. Pour ce faire, vous pouvez utiliser l’Assistant Déploiement et il n’est fait qu’une seule fois pour le domaine. Cela est dû au fait que le processus crée des groupes et modifie le domaine, et vous ne devez effectuer cette opération qu’une seule fois.
    
- [Créer des enregistrements DNS pour Skype entreprise Server](create-dns-records.md) : pour que Skype entreprise Server fonctionne correctement, un certain nombre de paramètres DNS doivent être mis en place. Cela permet aux clients de savoir comment accéder aux services et que les serveurs connaissent les uns des autres. Ces paramètres ne doivent être exécutés qu’une seule fois par déploiement, car une fois que vous avez affecté une entrée DNS, celle-ci est disponible dans l’ensemble du domaine.
    
- [Créer et publier une nouvelle topologie dans Skype entreprise Server](create-and-publish-new-topology.md) : avant de pouvoir installer le système Skype entreprise Server sur chacun des serveurs de la topologie, vous devez créer une topologie et la publier. Lorsque vous publiez une topologie, vous chargez les informations de topologie dans la base de données du magasin central de gestion. S’il s’agit d’un pool Enterprise Edition, vous créez la base de données du magasin central de gestion la première fois que vous publiez une nouvelle topologie. S’il s’agit de la version Standard Edition, vous devez exécuter le processus prepare First Standard Edition Server à partir de l’Assistant Déploiement avant de publier une topologie. Cela prépare la version Standard Edition en installant une instance de SQL Server Express Edition et en créant le magasin central de gestion.
    
- [Installez Skype entreprise Server sur les serveurs de la topologie](install-skype-for-business-server.md) : une fois que la topologie est chargée dans le magasin central de gestion et que Active Directory sait quels serveurs effectueront quels rôles, vous devez installer le système Skype entreprise Server sur chacun des serveurs de la topologie.
    
- [Vérifiez la topologie dans Skype entreprise Server](verify-the-topology.md) : une fois que la topologie est publiée et que les composants du système Skype entreprise Server sont installés sur chacun des serveurs de la topologie, vous êtes prêt à vérifier que la topologie fonctionne comme prévu. Cela inclut le fait de vérifier que la configuration a été propagée sur tous les serveurs Active Directory afin que l’ensemble du domaine sache que Skype entreprise est disponible dans le domaine.
    

