---
title: Liste de contrôle du déploiement du contrôle d’admission des appels
TOCTitle: Liste de contrôle du déploiement du contrôle d’admission des appels
ms:assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398928(v=OCS.15)
ms:contentKeyID: 49298968
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Liste de contrôle du déploiement du contrôle d’admission des appels

 

_**Dernière rubrique modifiée :** 2012-10-22_

Servez-vous de la liste de contrôle suivante pour vérifier que vous avez exécuté toutes les tâches de configuration nécessaires au déploiement du contrôle d’admission des appels (CAC).

  - Si un ou plusieurs serveurs Edge sont déployés, chaque adresse IP de l’interface externe doit être ajoutée à la liste de sous-réseaux dans les paramètres de configuration réseau, avec un masque de 32 bits. Vous devez également associer ce sous-réseau (adresse IP) à l’ID de site réseau pour l’emplacement géographique où est déployé le service Edge A/V.
    
    > [!NOTE]  
    > Il n’est pas obligatoire que les serveurs Edge implémentent le contrôle d’admission des appels.

  - Vérifiez que le contrôle d’admission des appels est activé, soit en ouvrant le Panneau de configuration Lync Server, soit en exécutant la cmdlet, comme spécifié dans la section [Activer le contrôle d’admission des appels](lync-server-2013-enable-call-admission-control.md). .

  - Vérifiez que le contrôle d’admission des appels est activé sur tous les sites centraux. Pour ce faire, vous pouvez faire appel au Générateur de topologie. Si un avertissement s’affiche lors de la publication, ne l’ignorez *pas*.

  - Vérifiez que tous les sous-réseaux qui sont gérés dans le réseau d’entreprise sont configurés dans les paramètres de configuration réseau. Chaque sous-réseau doit impérativement être associé à un site réseau, comme expliqué dans la section [Association d’un sous-réseau à un site réseau dans Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).

  - Vérifiez que les adresses IP ou de sous-réseau de tous les serveurs frontaux, SBA (Survivable Branch Appliances), serveurs de conférence Audio/Vidéo (s’ils figurent dans un pool distinct) et serveurs de médiation sont configurées dans les paramètres de configuration réseau.

