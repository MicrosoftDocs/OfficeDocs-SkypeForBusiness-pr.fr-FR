---
title: Modification de la topologie dans Skype Entreprise Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 4/5/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 47425ab1-5645-4d6f-b202-64bcce43e3ef
description: Après avoir répondu aux questions initiales, vous pouvez modifier le nom de domaine complet et les adresses IP pour le site. Pour ce faire, sur la page de la topologie globale, double-cliquez sur le site que vous souhaitez modifier.
ms.openlocfilehash: 7de778c9aed8594df4fc70f9a6635bd0c21c6db4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="edit-the-topology-in-skype-for-business-server-2015"></a>Modification de la topologie dans Skype Entreprise Server 2015
 
Après avoir répondu aux questions initiales, vous pouvez modifier le nom de domaine complet et les adresses IP pour le site. Pour cela, sur la page **Topologie globale**, double-cliquez sur le site que vous souhaitez modifier.
  
L’outil de planification affiche la topologie de site pour le site sélectionné. Le bas de la page du site comporte quatre onglets :
  
![Outil de planification - Topologie de site](../../media/Planning_Tool_Site_Topology.png)
  
- Topologie de site - la page actuellement affichée avec une présentation visuelle de la topologie, comme recommandé.
    
- Diagramme de réseau de bord - la page de diagramme de réseau de bord est où le concepteur la plupart du travail de l’outil de planification. Le diagramme affiche la configuration réseau pour un Skype recommandée pour la topologie de Business Server 2015, avec des entrées modifiables pour IP adresses et noms de domaine complets pour serveurs, pool et à la fois matérielle et système de nom de domaine (DNS) les équilibreurs de charge.
    
- Rapport Admin de bord - le rapport Admin de bord contient un total de quatre états :
    
     ![Page Rapport d’administrateur Edge](../../media/Planning_Tool_Summary_Report.png)
  
  - Rapport de synthèse - un rapport général de paramètres pour la configuration de réseau de bord. Si vous calez les valeurs de la page **Diagramme du réseau de périmètre** sur les valeurs des adresses TCP/IP et des noms de domaine complets qui seront utilisées dans la topologie du déploiement, ces adresses et noms seront représentés ici. Sinon, les valeurs par défaut s’afficheront.
    
  - Certificat de rapports - répertorie le nom du sujet et les noms d’objet alternatifs pour les certificats qui sont requis pour la topologie de l’état du certificat.
    
  - État du pare-feu - l’état du pare-feu répertorie les informations nécessaires à la configuration des pare-feu de périmètre dans l’infrastructure. Il s’agit des adresses IP (valeurs par défaut ou valeurs modifiées), des rôles serveur, des ports et adresses IP source et de destination, des protocoles de transport, des protocoles d’application et de remarques pertinentes.
    
  - DNS - l’état DNS reprend des informations pertinentes pour les entrées DNS qui vous devez le créer. Il s’agit du type d’enregistrement, du nom de domaine complet, de l’adresse IP et de commentaires nécessaires pour le bon fonctionnement du déploiement.
    
- Résumé du site - le résumé du site présente une vue d’ensemble des sélections que vous avez apportées en répondant aux questions initiales ou en renseignant les valeurs de **Concevoir des Sites**. Les informations de capacité sont également présentées. 
    
    > [!NOTE]
    > Les informations sur la page Résumé du site sont propres à chaque conception. Par conséquent, certaines sections et informations détaillées ici peuvent ne pas s’afficher pour certaines conceptions. 
  
## <a name="edit-the-network-configuration-diagram"></a>Modifier le diagramme de configuration du réseau
<a name="Edit_Network_diagram"> </a>

La plupart du travail par un concepteur dans la Skype pour outil de planification de 2015 Business Server consiste à définir les entrées pour les adresses IP et les noms de domaine pleinement qualifié (FQDN) pour les écritures sur le réseau de tâches. Les informations entrées sur cette page porte également ses fruits dans les rapports et les autres informations contenues dans l’outil de planification. 
  
![Outil de planification - Diagramme réseau](../../media/Planning_Tool_Network_Diagram.png)
  
L’outil de planification crée un diagramme de réseau avec un texte par défaut pour les adresses IP et noms de domaine complets. 
  
Pour modifier le diagramme de réseau et les valeurs entrées :
  
1. Commencez par choisir une section du réseau. Par exemple, double-cliquez sur le texte **access1.contoso.com**. Dans la boîte de dialogue qui s’ouvre, tapez le nom de domaine complet (FQDN) réel du serveur access1.contoso.com et l’adresse IP réelle, en remplaçant 131.107.155.3.
    
2. Cliquez sur **OK** pour enregistrer les entrées.
    
3. Continuez à modifier les adresses IP et les noms de domaine complets (FQDN) en spécifiant des adresses IP virtuelles pour les programmes d’équilibrage de la charge matérielle ou des entrées de serveur pour l’équilibrage de la charge DNS des serveurs contenus dans les pools.
    
Une fonction utile de l’outil de planification est la possibilité d’affecter une plage d’adresses IP et de noms d’hôte de serveur, au lieu de demander au concepteur de modifier chaque serveur d’un pool. Par exemple :
  
1. Double-cliquez sur les serveurs frontaux du pool. Quand la boîte de dialogue s’ouvre, sélectionnez **Souhaitez-vous utiliser les adresses IP et les noms de domaine complets (FQDN) comme points de départ pour tous les serveurs équivalents dans ce cluster ?**. 
    
2. Dans l’exemple, la valeur de démarrage pour le premier serveur est fe0101.contoso.com avec l’adresse IP 192.168.21.122.
    
3. Tapez fe0.contoso.com dans le **FQDN de serveur frontal fin**, 192.168.21.131 dans **l’adresse IP de serveur avant fin**et puis cliquez sur **OK**.
    
4. La fonction d’incrémentation automatique met à jour tous les serveurs du pool entre fe01 et fe06, et toutes les adresses IP entre 192.168.21.131 et 136.
    
Une fois toutes les modifications terminées, enregistrez la topologie en procédant comme suit : 
  
Pour enregistrer la conception de l’outil de planification, cliquez sur **fichier**, puis cliquez sur **Enregistrer la topologie** ou **Enregistrer la topologie sous**. Si une boîte de dialogue **Enregistrer l’outil de planification sous** s’affiche, tapez un nom pour le fichier dans **Nom de fichier**, puis cliquez sur **Enregistrer**. 
  
## <a name="see-also"></a>Voir aussi
<a name="Edit_Network_diagram"> </a>

#### 

[Modification de la conception](http://technet.microsoft.com/library/08f639ba-0e5f-4ae7-9191-c3d96c25b169.aspx)

