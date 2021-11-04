---
title: Modifier la topologie dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 47425ab1-5645-4d6f-b202-64bcce43e3ef
description: Après avoir répondu aux questions initiales, vous pouvez modifier le nom de domaine complet (FQDN) et les adresses IP du site. Pour cela, sur la page Topologie globale, double-cliquez sur le site que vous souhaitez modifier.
ms.openlocfilehash: 2276f2959329c77744054976e3a49f5ad72778ae
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60776164"
---
# <a name="edit-the-topology-in-skype-for-business-server-2015"></a>Modifier la topologie dans Skype Entreprise Server 2015

Après avoir répondu aux questions initiales, vous pouvez modifier le nom de domaine complet (FQDN) et les adresses IP du site. Pour cela, sur la page **Topologie globale**, double-cliquez sur le site que vous souhaitez modifier.

L’outil de planification affiche la topologie de site pour le site sélectionné. Le bas de la page du site comporte quatre onglets :

![Topologie du site de l’outil de planification.](../../media/Planning_Tool_Site_Topology.png)

- Topologie de site : page actuellement affichée avec une vue d’ensemble visuelle de la topologie, comme recommandé.

- Réseau de réseau de périphérie - La page Réseau de réseau de périphérie est l’endroit où le concepteur fait la majeure partie du travail dans l’outil de planification. Le diagramme affiche la configuration réseau pour une topologie Skype Entreprise Server 2015 recommandée, avec des entrées modifiables pour les adresses IP et les noms de domaine complets pour les serveurs, le pool et les équilibreurs de charge matériels et DNS (Domain Name System).

- Rapport d’administration Edge - Le rapport d’administration Edge contient un total de quatre rapports :

     ![Page Rapport d’administration Edge.](../../media/Planning_Tool_Summary_Report.png)

  - Rapport de synthèse : rapport général sur les paramètres de configuration du réseau Edge. Si vous modifiez les valeurs de la **page** Réseau de réseau de périphérie en valeurs de topologie TCP/IP et FQDN qui seront utilisées dans le déploiement réel, ces adresses et noms seront représentés ici. Sinon, le texte par défaut s’affiche.

  - Rapport de certificat : le rapport de certificats indique le nom du sujet et les autres noms du sujet pour les certificats requis pour la topologie.

  - Rapport de pare-feu : le rapport de pare-feu répertorie les informations nécessaires pour configurer les pare-feu de périmètre dans l’infrastructure. Cela inclut les adresses IP (valeurs par défaut ou modifiées), le rôle serveur, l’adresse IP source et le port, l’adresse IP et le port de destination, le protocole de transport, le protocole d’application et les notes pertinentes.

  - Rapport DNS : le rapport DNS répertorie les informations pertinentes pour les entrées DNS que vous devez créer. Il s’agit du type d’enregistrement, du nom de domaine complet, de l’adresse IP et de commentaires nécessaires pour le bon fonctionnement du déploiement.

- Résumé du site : le résumé du site présente une vue d’ensemble des sélections que vous avez réalisées en répondant aux questions initiales ou en remplissant les valeurs des sites de **conception.** Des informations sur la capacité sont également présentées.

    > [!NOTE]
    > Les informations sur la page Résumé du site sont propres à chaque conception. Par conséquent, certaines sections et informations détaillées ici peuvent ne pas apparaître pour certaines conceptions.

## <a name="edit-the-network-configuration-diagram"></a>Modifier le diagramme de configuration réseau
<a name="Edit_Network_diagram"> </a>

La majeure partie du travail qu’un concepteur fait dans l’outil de planification Skype Entreprise Server 2015 consiste à définir les entrées pour les adresses IP et les noms de domaine complets (FQDN) pour les entrées sur le diagramme réseau. Les informations entrées sur cette page sont contenues dans les rapports et les autres informations contenues dans l’outil de planification.

![Diagramme réseau de l’outil de planification.](../../media/Planning_Tool_Network_Diagram.png)

L’outil de planification crée un diagramme réseau avec du texte par défaut pour les adresses IP et les noms de groupe.

Pour modifier le diagramme de réseau et les valeurs entrées :

1. Choisissez la section du réseau sur laquelle vous souhaitez commencer à travailler. Par exemple, double-cliquez sur le **texte, access1.contoso.com**. Dans la boîte de dialogue qui s’ouvre, tapez le nom deqdn réel du serveur access1.contoso.com et l’adresse IP réelle, en remplaçant le 131.107.155.3.

2. Cliquez sur **OK** pour enregistrer les entrées.

3. Continuez à modifier les adresses IP et les noms de domaine complets (FQDN) en spécifiant des adresses IP virtuelles pour les programmes d’équilibrage de la charge matérielle ou des entrées de serveur pour l’équilibrage de la charge DNS des serveurs contenus dans les pools.

Une fonction utile de l’outil de planification est la possibilité d’affecter une plage d’adresses IP et de noms d’hôte de serveur, au lieu de demander au concepteur de modifier chaque serveur d’un pool. Par exemple :

1. Double-cliquez sur les serveurs frontaux du pool. Lorsque la boîte de dialogue s’ouvre, sélectionnez **Souhaitez-vous utiliser les adresses IP et les noms de domaine complets (FQDN) comme points de départ pour tous les serveurs équivalents dans ce cluster ?**.

2. Par exemple, la valeur de départ du premier serveur est fe0101.contoso.com et l’adresse IP 192.168.21.122.

3. Tapez fe0.contoso.com **FQDN** du serveur frontal, tapez 192.168.21.131 dans l’adresse IP du serveur **frontal,** puis cliquez sur **OK.**

4. La fonctionnalité d’incrémentation automatique met à jour tous les serveurs du pool vers fe01 à fe06, et toutes les adresses IP de 192.168.21.131 à 136.

Une fois toutes les modifications terminées, enregistrez la topologie en effectuant les étapes suivantes :

Pour enregistrer la conception de l’outil de planification, cliquez sur **Fichier,** puis sur Enregistrer la **topologie** ou **Enregistrer la topologie sous**. Si une boîte de dialogue **Enregistrer l’outil de planification sous le nom** s’affiche, tapez un nom pour le fichier dans **Nom du fichier**, puis cliquez sur **Enregistrer**.

## <a name="see-also"></a>Voir aussi
<a name="Edit_Network_diagram"> </a>

[Modification de la conception](/previous-versions/office/lync-server-2013/lync-server-2013-editing-the-design)