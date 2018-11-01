---
title: "Marquer une app. serv. MSPL comme critique ou non critique"
TOCtitle: "Marquer une app. serv. MSPL comme critique ou non critique"
ms:assetid: df68fdc6-b7e6-4f07-acdc-0cd4c2c888a1
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg182598(v=OCS.15)
ms:contentKeyID: 49299095
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Marquer une application serveur Microsoft SIP Processing Language (MSPL) comme critique ou non critique

 

_**Dernière rubrique modifiée :** 2012-11-01_

Les applications serveur Microsoft SIP Processing Language (MSPL) sont des applications script uniquement utilisant le langage de script MSPL au lieu de API Microsoft Lync 2010. Certaines applications serveur MSPL sont spécifiées comme critiques. Si un script est critique, il doit être lancé au démarrage du système afin que Lync Server 2013 puisse démarrer. Si le script échoue pendant l’exécution de Lync Server, le serveur ne s’arrête pas, mais il cesse l’envoi de trafic vers le script et consigne des erreurs dans le journal des événements.

Vous pouvez utiliser le Panneau de configuration Lync Server pour marquer ou démarquer les applications serveur Microsoft SIP Processing Language (MSPL) comme critiques.

Les scripts ne prennent pas tous en charge cette option. Par exemple, le script DefaultRouting est marqué comme critique, et cette option ne peut pas être modifiée pour DefaultRouting.

## Pour marquer ou démarquer une application serveur MSPL comme critique

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Topologie**, puis sur **Application de serveur**.

4.  Dans la page **Application de serveur**, cliquez sur l’en-tête d’une colonne pour trier les applications, si nécessaire, puis sur l’application de serveur à modifier.

5.  Cliquez sur **Action**.

6.  Cliquez sur **Marquer comme critique** ou **Désélectionner comme critique** (si le script prend en charge cette option).

## Voir aussi

#### Tâches

[Activer ou désactiver une application de serveur MSPL (Microsoft SIP Processing Language)](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  

#### Concepts

[Afficher des applications de serveur MSPL (Microsoft SIP Processing Language) dans Lync Server 2013](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  

#### Autres ressources

[Gestion de la topologie Lync Server 2013](lync-server-2013-managing-the-lync-server-topology.md)

