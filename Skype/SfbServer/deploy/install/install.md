---
title: Installation de Skype Entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 71299b34-8783-4384-9949-0d3162c8a36e
description: 'Résumé: Découvrez comment préparer votre environnement pour l’installation de Skype entreprise Server. Télécharger une version d’évaluation gratuite de Skype entreprise Server à partir du centre d’évaluation https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverMicrosoft pour:.'
ms.openlocfilehash: b9a89e73f47922493a6d7add320c21b9b9900103
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306775"
---
# <a name="install-skype-for-business-server"></a>Installation de Skype Entreprise Server
 
**Résumé:** Découvrez comment préparer votre environnement pour l’installation de Skype entreprise Server. Télécharger une version d’évaluation gratuite de Skype entreprise Server à partir du centre d’évaluation[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)Microsoft pour:.
  
Cet article vous guide tout au long du processus d’installation de Skype entreprise Server. Cet article ne couvre pas toutes les procédures dont vous avez besoin pour effectuer une installation complète de Skype entreprise Server. Son but est de fournir des exemples de procédures dans une topologie étroitement définie, qui comprend les fonctionnalités standard de réunion et de partage.
  
## <a name="overview-of-the-install-process-for-skype-for-business-server"></a>Vue d’ensemble du processus d’installation de Skype entreprise Server

Une installation de Skype entreprise Server comporte différentes procédures. Les procédures dont vous avez besoin pour obtenir Skype entreprise Server en cours d’exécution dans votre environnement varient en fonction des spécificités de votre environnement. Par exemple, si vous utilisez Windows Server pour le DNS, vous pourrez tirer parti de l’exemple de procédure pour l’ajout d’une entrée DNS. Si vous utilisez un autre système pour le DNS, vous devez suivre les procédures de votre système DNS particulier. Ceci est vrai pour de nombreuses procédures de cette section.
  
Skype entreprise Server est disponible en Standard Edition et Enterprise Edition. La principale différence réside dans le fait que Standard Edition ne prend pas en charge les fonctionnalités de haute disponibilité qui sont incluses dans la version Enterprise Edition. 
  
Skype entreprise Server est un produit avancé, et le processus d’installation exact dépend de vos circonstances spécifiques. Cette section vous guide tout au long des étapes générales pour installer le produit. Toutefois, chaque procédure peut varier en fonction de votre environnement et de vos décisions de planification. Par exemple, pour les petites organisations, un serveur unique et l’exécution de Skype entreprise Server Standard Edition peuvent être appropriés, tandis qu’une grande organisation multinationale peut avoir des serveurs 50 aux endroits où se trouve le produit.
  
> [!NOTE]
> Pour en savoir plus sur les dernières mises à jour cumulatives, reportez-vous à la rubrique [mises à jour de Skype entreprise Server](https://support.microsoft.com/en-us/kb/3061064). Après avoir installé le correctif CU1, un administrateur doit exécuter `Update-CsAdminRole` l’applet de demande. Cette applet de commande est nécessaire pour accéder aux nouvelles applets de commande GCP via Remote PowerShell.
  
> [!IMPORTANT]
> Les procédures de cette section sont destinées à servir d’exemple en utilisant un ensemble étroitement défini d’exigences et en supposant que des décisions spécifiques ont déjà été prises. Les procédures réelles nécessaires à l’installation de Skype entreprise Server peuvent être très différentes. Suivez les procédures décrites dans cette section en guise d’exemple uniquement et non sous la forme d’un guide pas à pas pour l’installation de Skype entreprise Server dans chaque environnement. 
  
La première fois que vous exécutez Skype entreprise Server implique huit étapes principales. Nous vous conseillons de comprendre que les procédures d’exemple de cette section ne sont pas les seules procédures requises pour l’installation de Skype entreprise Server. Les huit étapes suivantes sont simplement des exemples permettant de mieux comprendre l’ensemble du processus et d’obtenir un environnement de travail de base opérationnel. Vous pouvez effectuer les étapes 1 à 5 dans un ordre quelconque. Cependant, vous devez exécuter les étapes 6, 7 et 8 dans l’ordre et après les étapes 1 à 5 comme indiqué dans le diagramme. Les huit étapes sont les suivantes :
  
![Vue d’ensemble de la procédure d’installation.](../../media/b1a59b39-a7f0-4781-ac4d-2dfef7ca3700.png)
  
- [Installation des conditions préalables pour Skype entreprise Server](install-prerequisites.md) : installation requise sur tous les serveurs qui constituent la topologie de Skype entreprise Server. Notez que les prérequis ne sont pas les mêmes pour tous les rôles. Par exemple, les serveurs qui fourniront le rôle frontal présentent un ensemble de prérequis et les serveurs qui fourniront un rôle de Directeur présentent un autre ensemble de prérequis. Consultez la documentation de planification des prérequis pour plus de détails.
    
- [Création d’un partage de fichiers dans Skype entreprise Server](create-a-file-share.md) : création d’un partage de fichiers qui sera utilisé par les serveurs dans la topologie de Skype entreprise Server.
    
- [Installer les outils d’administration dans Skype entreprise Server](install-administrative-tools.md) : les outils d’administration incluent le générateur de topologie et le panneau de configuration. Vous devez installer les outils d’administration sur au moins un serveur dans la topologie ou une station de travail de gestion 64 bits exécutant une version de système d’exploitation Windows qui est prise en charge par Skype entreprise Server.
    
- [Préparer Active Directory pour Skype entreprise Server](prepare-active-directory.md) : Skype entreprise Server fonctionne étroitement avec Active Directory. Vous devez préparer le domaine Active Directory pour qu’il fonctionne avec Skype entreprise Server. Vous pouvez effectuer ce processus dans l’assistant Déploiement, et ce processus n’est effectué qu’une seule fois pour le domaine. Ceci est dû au fait que le processus crée des groupes et modifie le domaine et vous n’avez besoin d’effectuer cette opération qu’une seule fois.
    
- [Créer des enregistrements DNS pour Skype entreprise Server](create-dns-records.md) : pour que Skype entreprise Server fonctionne correctement, un certain nombre de paramètres DNS doivent être mis en place. Ceci afin que les clients sachent comment accéder aux services et que les serveurs se connaissent entre eux. Ces paramètres ne doivent être définis qu’une seule fois par déploiement, car, dans la mesure où vous attribuez une entrée DNS, elle est disponible dans tout le domaine.
    
- [Créer et publier une nouvelle topologie dans Skype entreprise Server](create-and-publish-new-topology.md) : avant de pouvoir installer le système Skype entreprise Server sur chacun des serveurs de la topologie, vous devez créer une topologie et la publier. Lorsque vous publiez une topologie, vous chargez les informations dans la base de données du magasin central de gestion. S’il s’agit d’un pool Enterprise Edition, vous créez la base de données du magasin central de gestion la première fois que vous publiez une nouvelle topologie. S’il s’agit de l’édition standard, vous devez exécuter le processus préparer le premier serveur édition standard à partir de l’Assistant Déploiement avant de publier une topologie. Il prépare l’installation de Standard Edition en installant une instance de SQL Server Express Edition et en créant le magasin central de gestion.
    
- [Installation de Skype entreprise Server sur des serveurs dans la topologie](install-skype-for-business-server.md) : une fois que la topologie est chargée dans le magasin de gestion central et qu’Active Directory sait quels serveurs utiliseront les rôles, vous devez installer le système Skype entreprise Server sur chacun de serveurs de la topologie.
    
- [Vérifier la topologie dans Skype entreprise Server](verify-the-topology.md) : une fois que vous avez publié la topologie et les composants du système Skype entreprise Server installés sur chacun des serveurs de la topologie, vous êtes prêt à vérifier que la topologie fonctionne correctement. Pour cela, vous devez vérifier que la configuration a été propagée sur tous les serveurs Active Directory de sorte que le domaine complet sache que Skype entreprise est disponible dans le domaine.
    

