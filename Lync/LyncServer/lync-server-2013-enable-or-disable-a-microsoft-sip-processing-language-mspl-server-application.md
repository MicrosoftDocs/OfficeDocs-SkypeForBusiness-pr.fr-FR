---
title: "Act. ou dés une app. de serveur MSPL (Microsoft SIP Processing Language)"
TOCtitle: "Act. ou dés une app. de serveur MSPL (Microsoft SIP Processing Language)"
ms:assetid: b20af38d-224a-4459-991d-0b7eabb3ca7c
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg182573(v=OCS.15)
ms:contentKeyID: 49298579
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Activer ou désactiver une application de serveur MSPL (Microsoft SIP Processing Language)

 

_**Dernière rubrique modifiée :** 2012-09-21_

Vous pouvez utiliser le Panneau de configuration Lync Server pour activer ou désactiver les applications serveur MSPL (Microsoft SIP Processing Language) exécutées dans votre environnement Lync Server 2013. Ces applications script uniquement utilisent un langage de script au lieu de l’API de prévisualisation Microsoft Lync 2013.

Il n’est pas possible d’activer ou de désactiver tous les scripts. Par exemple, le script DefaultRouting est activé et ce paramètre ne peut pas être modifié pour DefaultRouting.

## Pour activer ou désactiver une application serveur MSPL

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Topologie**, puis sur **Application de serveur**.

4.  Dans la page **Application de serveur**, cliquez sur l’en-tête d’une colonne pour trier les applications, si nécessaire, puis sur l’application de serveur à modifier.

5.  Cliquez sur **Action**.

6.  Cliquez sur **Activer l’application** ou sur **Désactiver l’application** (si le script prend en charge cette option).

## Voir aussi

#### Tâches

[Marquer une application serveur Microsoft SIP Processing Language (MSPL) comme critique ou non critique](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)  

#### Concepts

[Afficher des applications de serveur MSPL (Microsoft SIP Processing Language) dans Lync Server 2013](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  

#### Autres ressources

[Gestion de la topologie Lync Server 2013](lync-server-2013-managing-the-lync-server-topology.md)

