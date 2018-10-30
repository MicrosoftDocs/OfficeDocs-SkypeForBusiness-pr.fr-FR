---
title: Topologies pour les téléphones IP
TOCTitle: Topologies pour les téléphones IP
ms:assetid: 26ebffcf-43ff-4e70-847d-0fbc90e94e57
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg425740(v=OCS.15)
ms:contentKeyID: 49296630
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Topologies pour les téléphones IP

 

_**Dernière rubrique modifiée :** 2012-06-21_

Cette section fournit une vue d’ensemble du processus de connexion et explique les différences qui existent entre le mode de connexion d’un téléphone IP à un réseau interne ou externe.

> [!NOTE]  
> Lync Server prend en charge les téléphones IP suivants : le téléphone de partie commune Aastra 6721ip, le téléphone de bureau Aastra 6725ip, le téléphone IP HP 4110 (téléphone de partie commune), le téléphone IP HP 4120 (téléphone de bureau), le téléphone de bureau IP Polycom CX600, le téléphone de bureau IP Polycom CX700, le téléphone de partie commune IP Polycom CX500 et le téléphone de conférence IP Polycom CX3000. Parmi tous ces téléphones, seul le Polycom CX700 peut exécuter Lync Phone Edition.

Le diagramme suivant décrit tous les composants impliqués dans la connectivité d’appareil au sein d’un environnement d’entreprise.

**Topologie interne**

![Périphériques à l’intérieur du réseau](images/Gg425740.3d88893e-df57-46e3-855a-a1d24589030a(OCS.15).jpg "Périphériques à l’intérieur du réseau")

> [!NOTE]  
> L’illustration précédente est une représentation logique, et non une vue d’ensemble physique. Par exemple, les services de domaine Active Directory (AD DS) sont rarement situés sur le même ordinateur que les autres composants Lync Server. Le magasin d’utilisateurs peut être situé sur le serveur principal ou sur les serveurs d’archivage et de surveillance. Lync Server Management Shell, le serveur web et les services de mise à jour font tous partie du rôle serveur frontal.

Le diagramme suivant fournit une vue d’ensemble des composants impliqués lorsque l’appareil est situé à l’extérieur du réseau d’entreprise.

**Topologie externe**

![Périphériques à l’extérieur du réseau](images/Gg425740.8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3(OCS.15).jpg "Périphériques à l’extérieur du réseau")

> [!NOTE]  
> Le service web de mise à jour des appareils fournit un site web externe et interne, mais seul le site externe est indiqué ici.<br />
L’emplacement du serveur d’inscriptions et l’URL du service web de mise à jour des appareils pour l’organisation doivent être publiés dans le système DNS si l’accès externe doit être activé. Par ailleurs, le serveur Edge doit être déployé et correctement configuré afin d’autoriser les communications externes à partir de l’appareil vers l’environnement d’entreprise et vice-versa. Cela n’apparaît pas sur le diagramme précédent car le déploiement du serveur Edge n’est pas effectué en fonction de la connectivité de l’appareil.
