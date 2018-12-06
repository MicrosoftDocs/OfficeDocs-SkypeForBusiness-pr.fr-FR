---
title: 'Lync Server 2013 : Modification de la conception'
TOCTitle: Modification de la conception
ms:assetid: 08f639ba-0e5f-4ae7-9191-c3d96c25b169
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg558608(v=OCS.15)
ms:contentKeyID: 53095355
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Modification de la conception dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-02-21_

Après avoir répondu aux questions initiales, vous pouvez modifier le nom de domaine complet et les adresses IP pour le site. Pour cela, sur la page **Topologie globale** , double-cliquez sur le site que vous souhaitez modifier.

L’outil de planification affiche la topologie du site sélectionné. Le bas de la page du site comporte quatre onglets :

![Outil de planification - Topologie de site](images/Gg558608.e6189c20-360a-42bd-ba90-11bdb5b7551b(OCS.15).jpg "Outil de planification - Topologie de site")

  - Topologie du site - La page affichée avec une représentation visuelle de la topologie recommandée.

  - Diagramme du réseau de périmètre - Cette page regroupe la plupart des tâches que le concepteur doit effectuer dans l’outil de planification. Le diagramme présente la configuration réseau d’une topologie Lync Server 2013 recommandée, avec des entrées modifiables pour les adresses IP et les noms de domaine complets pour les serveurs, les pools et les équilibreurs de charge matériels et DNS.

  - Rapport de l’administrateur du périmètre - Ce rapport contient quatre rapports :
    
    ![Page Rapport d’administrateur Edge](images/Gg558608.0019cc5e-af39-4cb9-82ce-58f6388242ff(OCS.15).jpg "Page Rapport d’administrateur Edge")  
    
      - Rapport récapitulatif - Rapport général des paramètres de la configuration du réseau de périmètre. Si vous calez les valeurs de la page **Diagramme du réseau de périmètre** sur les valeurs des adresses TCP/IP et des noms de domaine complets qui seront utilisées dans la topologie du déploiement, ces adresses et noms seront représentés ici. Sinon, les valeurs par défaut s’afficheront.
    
      - Rapport sur les certificats - Ce rapport répertorie les noms de sujet et les noms de sujet alternatifs requis pour la topologie.
    
      - Rapport sur les pare-feu - Ce rapport répertorie les informations nécessaires pour configurer les pare-feu du périmètre dans l’infrastructure. Il s’agit des adresses IP (valeurs par défaut ou valeurs modifiées), des rôles serveur, des ports et adresses IP source et de destination, des protocoles de transport, des protocoles d’application et de remarques pertinentes.
    
      - Rapport DNS - Ce rapport répertorie les informations pertinentes pour les entrées DNS que vous devez créer. Il s’agit du type d’enregistrement, du nom de domaine complet, de l’adresse IP et de commentaires nécessaires pour le bon fonctionnement du déploiement.

  - Résumé du site - Le résumé du site présente une vue d’ensemble des sélections que vous avez effectuées en répondant aux questions initiales ou en indiquant les valeurs dans **Concevoir des sites** . Les informations de capacité sont également présentées
    
    > [!NOTE]  
    > Les informations sur la page Résumé du site sont propres à chaque conception. Par conséquent, certaines sections et informations détaillées ici peuvent ne pas s’afficher pour certaines conceptions.

## Voir aussi

#### Concepts

[Modification du diagramme de configuration du réseau dans Lync Server 2013](lync-server-2013-editing-the-network-configuration-diagram.md)

