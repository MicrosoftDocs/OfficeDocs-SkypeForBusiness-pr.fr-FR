---
title: "Lync Server 2013 : Créa. stratégie de routage VoIP pr les util. de succursale"
TOCTitle: Création de la stratégie de routage VoIP pour les utilisateurs de succursale
ms:assetid: 10deca9f-f870-4a42-b25d-e4fc53108658
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398196(v=OCS.15)
ms:contentKeyID: 49296290
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Création de la stratégie de routage VoIP pour les utilisateurs de succursale dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-23_

Nous vous recommandons de créer une stratégie de Voix sur IP (VoIP) distincte pour les utilisateurs sur des sites de succursale. Cette stratégie doit contenir les itinéraires de sortie de la passerelle du Survivable Branch Appliance ou de la passerelle externe du serveur Survivable Branch Server et les itinéraires de sauvegarde de sortie d’une passerelle sur le site central. Quel que soit l’endroit où l’utilisateur est enregistré, soit sur le Serveur d’inscriptions sur le Survivable Branch Appliance ou le serveur Survivable Branch Server, soit sur le cluster des serveurs d’inscriptions de sauvegarde sur le site central, la stratégie VoIP de l’utilisateur est toujours appliquée.

## Pour configurer la stratégie de routage VoIP pour les utilisateurs de sites de succursale

1.  Créez un plan de numérotation utilisateur et affectez-le aux utilisateurs. (Reportez-vous à [Création d’un plan de numérotation dans Lync Server 2013](lync-server-2013-create-a-dial-plan.md) dans la documentation des opérations.)

2.  Affectez les règles de normalisation correspondantes aux habitudes de numérotation des utilisateurs sur ce site. Si le Survivable Branch Appliance ou le serveur Survivable Branch Server ne sont pas disponibles et si l’utilisateur est inscrit sur le pool de serveurs d’inscriptions de sauvegarde du site central, le même plan de numérotation sera appliqué. (Reportez-vous à [Création d’un plan de numérotation dans Lync Server 2013](lync-server-2013-create-a-dial-plan.md) dans la documentation des opérations.)

3.  Configurez un itinéraire de sortie des communications vocales pour la passerelle du Survivable Branch Appliance ou la passerelle externe du serveur Survivable Branch Server. (Reportez-vous à [Créer un itinéraire de communications vocales dans Lync Server 2013](lync-server-2013-create-a-voice-route.md) dans la documentation des opérations.)

4.  Configurez un itinéraire d’appels de sauvegarde sur la passerelle du Survivable Branch Appliance ou du serveur Survivable Branch Server pointant vers le pool de serveurs d’inscriptions de sauvegarde (colocalisé avec le serveur de médiation) sur le site central. (Reportez-vous à la documentation du fabricant du Survivable Branch Appliance ou du serveur Survivable Branch Server.)
    
    > [!NOTE]  
    > Cet itinéraire de sauvegarde pour les appels garantit que l’utilisateur sur le site de succursale recevra les appels entrants qui lui sont destinés lorsque le Survivable Branch Appliance ou le serveur Survivable Branch Server n’est pas disponible (par exemple, s’il est arrêté pour maintenance). Si le serveur d’inscriptions et le serveur de médiation sur le Survivable Branch Appliance ou le serveur Survivable Branch Server ne sont pas disponibles et si l’utilisateur est inscrit sur le pool de serveurs d’inscriptions de sauvegarde du site central, les appels entrants seront quand même transmis à l’utilisateur.

**Étape suivante**  : [Configuration des paramètres de réacheminement de la messagerie vocale dans Lync Server 2013](lync-server-2013-configure-voice-mail-rerouting-settings.md)

