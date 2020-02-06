---
title: Modification de la topologie dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 47425ab1-5645-4d6f-b202-64bcce43e3ef
description: Après avoir répondu aux questions initiales, vous pouvez modifier le nom de domaine complet et les adresses IP pour le site. Pour cela, sur la page Topologie globale, double-cliquez sur le site que vous souhaitez modifier.
ms.openlocfilehash: dae99620f34b832dd4abe0baf83d6df11b388750
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816443"
---
# <a name="edit-the-topology-in-skype-for-business-server-2015"></a>Edit the topology in Skype for Business Server 2015

Après avoir répondu aux questions initiales, vous pouvez modifier le nom de domaine complet et les adresses IP pour le site. Pour cela, sur la page **Topologie globale**, double-cliquez sur le site que vous souhaitez modifier.

L’outil de planification affiche la topologie de site pour le site sélectionné. Le bas de la page du site comporte quatre onglets :

![Topologie de site outil de planification](../../media/Planning_Tool_Site_Topology.png)

- Topologie de site : page actuellement affichée avec une vue d’ensemble visuelle de la topologie recommandée.

- Diagramme de réseau Edge : la page réseau de tâches Edge est l’endroit où le concepteur effectue la majeure partie du travail dans l’outil de planification. Le diagramme affiche la configuration du réseau pour une topologie 2015 de Skype entreprise Server, avec des entrées modifiables pour les adresses IP et les noms de domaine complets pour les serveurs, le pool, et les équilibreurs de charge de matériel et de système de noms de domaine (DNS).

- Rapport d’administration Edge : le rapport d’administration Edge comporte au total quatre rapports :

     ![Page rapport d’administration Edge](../../media/Planning_Tool_Summary_Report.png)

  - Rapport de synthèse-un rapport général sur les paramètres de configuration du réseau Edge. Si vous calez les valeurs de la page **Diagramme du réseau de périmètre** sur les valeurs des adresses TCP/IP et des noms de domaine complets qui seront utilisées dans la topologie du déploiement, ces adresses et noms seront représentés ici. Sinon, les valeurs par défaut s’afficheront.

  - Rapport de certification-le rapport de certificat indique le nom de l’objet et les noms de remplacement de l’objet pour les certificats requis pour la topologie.

  - Rapport de pare-feu-le rapport de pare-feu recense les informations nécessaires à la configuration des pare-feux de périmètre dans l’infrastructure. Il s’agit des adresses IP (valeurs par défaut ou valeurs modifiées), des rôles serveur, des ports et adresses IP source et de destination, des protocoles de transport, des protocoles d’application et de remarques pertinentes.

  - Rapport DNS-le rapport DNS recense les informations pertinentes pour les entrées DNS que vous devez créer. Il s’agit du type d’enregistrement, du nom de domaine complet, de l’adresse IP et de commentaires nécessaires pour le bon fonctionnement du déploiement.

- Résumé du site-le résumé du site offre une vue d’ensemble des sélections que vous avez apportées en répondant aux questions d’une interview initiale ou en remplissant les valeurs des **sites de conception**. Les informations de capacité sont également présentées.

    > [!NOTE]
    > Les informations sur la page Résumé du site sont propres à chaque conception. Par conséquent, certaines sections et informations détaillées ici peuvent ne pas s’afficher pour certaines conceptions.

## <a name="edit-the-network-configuration-diagram"></a>Modifier le diagramme de configuration du réseau
<a name="Edit_Network_diagram"> </a>

La plupart des tâches que le concepteur effectue dans l’outil de planification de Skype entreprise Server 2015 consiste à définir les entrées pour les adresses IP et les noms de domaine complets (FQDN) pour les entrées sur le réseau de tâches. Les informations entrées dans cette page sont incluses dans les rapports et autres informations contenus dans l’outil de planification.

![Diagramme du réseau d’outils de planification](../../media/Planning_Tool_Network_Diagram.png)

L’outil de planification crée un diagramme de réseau avec le texte par défaut pour les adresses IP et les noms de domaine complets.

Pour modifier le diagramme de réseau et les valeurs entrées :

1. Commencez par choisir une section du réseau. Par exemple, double-cliquez sur le texte **access1.contoso.com**. Dans la boîte de dialogue qui s’ouvre, tapez le nom de domaine complet (FQDN) réel du serveur access1.contoso.com et l’adresse IP réelle, en remplaçant 131.107.155.3.

2. Cliquez sur **OK** pour enregistrer les entrées.

3. Continuez à modifier les adresses IP et les noms de domaine complets (FQDN) en spécifiant des adresses IP virtuelles pour les programmes d’équilibrage de la charge matérielle ou des entrées de serveur pour l’équilibrage de la charge DNS des serveurs contenus dans les pools.

Une fonction utile de l’outil de planification est la possibilité d’affecter une plage d’adresses IP et de noms d’hôte de serveur, au lieu de demander au concepteur de modifier chaque serveur d’un pool. Par exemple :

1. Double-cliquez sur les serveurs frontaux du pool. Quand la boîte de dialogue s’ouvre, sélectionnez **Souhaitez-vous utiliser les adresses IP et les noms de domaine complets (FQDN) comme points de départ pour tous les serveurs équivalents dans ce cluster ?**.

2. Dans l’exemple, la valeur de démarrage pour le premier serveur est fe0101.contoso.com avec l’adresse IP 192.168.21.122.

3. Tapez fe0.contoso.com dans le **nom de domaine complet du serveur frontal**, tapez 192.168.21.131 dans l’**Adresse IP du serveur frontal**, puis cliquez sur **OK**.

4. La fonction d’incrémentation automatique met à jour tous les serveurs du pool entre fe01 et fe06, et toutes les adresses IP entre 192.168.21.131 et 136.

Une fois toutes les modifications terminées, enregistrez la topologie en procédant comme suit :

Pour enregistrer la conception de l’outil de planification, cliquez sur **fichier**, puis sur **enregistrer la topologie** ou **enregistrer la topologie sous**. Si une boîte de dialogue **Enregistrer l’outil de planification sous** s’affiche, tapez un nom pour le fichier dans **Nom de fichier**, puis cliquez sur **Enregistrer**.

## <a name="see-also"></a>Voir aussi
<a name="Edit_Network_diagram"> </a>

[Editing the Design](https://technet.microsoft.com/library/08f639ba-0e5f-4ae7-9191-c3d96c25b169.aspx)
