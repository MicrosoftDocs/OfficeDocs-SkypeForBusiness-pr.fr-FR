---
title: Validation de la configuration d’Office Web Apps Server dans Lync Server 2013
TOCTitle: Validation de la configuration d’Office Web Apps Server
ms:assetid: f6e8ecbf-305d-4a13-92d0-b61dbd82b0ea
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205393(v=OCS.15)
ms:contentKeyID: 49299360
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Validation de la configuration d’Office Web Apps Server dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2014-04-22_

Une fois le serveur Office Web Apps ajouté à la topologie, et après la publication de cette topologie, deux nouveaux événements devraient s’afficher dans le journal d’événements de Lync Server. D’abord, un événement LS Data MCU (ID d’événement 41034) devrait être ajouté, cet événement va rapporter la découverte du serveur Office Web Apps :

**Web Conferencing Server WAC est découvert, le contenu PowerPoint est activé.**

En plus de cela, un autre événement LS Data MCU devrait être affiché (ID d’événement 41032), retournant les URL du serveur Office Web Apps. Par exemple, vous devriez voir un message semblable à :

**Web Conferencing Server WAC découvert avec succès.**

**Page du présentateur interne WAC : https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed=**

**Page du participant interne WAC : https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&=**

**Page du présentateur externe WAC : https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed**

**Page du participant interne WAC : https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&**

Si un événement LS Data MCU ayant l’ID d’événement 41033 s’affiche, cela signifie que la découverte d’Office Web Apps Server na pas fonctionné. Dans ce cas, Microsoft Lync Server 2013 essaiera autant de fois que nécessaire de découvrir la nouvelle configuration d’Office Web Apps Server. Si le processus de découverte ne fonctionne pas à chaque essai, nous vous conseillons de supprimer Office Web Apps Server de votre document de topologie, de publier la topologie mise à niveau, puis d’essayer de rajouter Office Web Apps Server à votre topologie une fois les problèmes de topologie résolus.

Si Office Web Apps Server semble configuré correctement et est reconnu par le processus de découverte, vous pouvez vérifier que Office Web Apps Server fonctionne correctement en partageant une présentation PowerPoint entre une paire de clients Microsoft Lync 2013. Si l’utilisateur A peut charger et afficher la présentation PowerPoint et si l’utilisateur B peut ensuite rejoindre la réunion et consulter la présentation, alors Office Web Apps Server fonctionne correctement.

Même si Office Web Apps Server semble être configuré correctement, il est possible que le message d’erreur suivant s’affiche : « Certaines fonctionnalités de partage ne sont pas disponibles en raison de problèmes de connectivité de serveur » lorsque vous essayez de partager une présentation PowerPoint. Si vous recevez ce message d’erreur, vous devez redémarrer le ou les serveurs frontaux associés à la nouvelle configuration d’Office Web Apps Server.

