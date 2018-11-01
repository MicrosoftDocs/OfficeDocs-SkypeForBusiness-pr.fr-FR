---
title: 'Lync Server 2013 : Activation du parcage d’appel pour les utilisateurs'
TOCTitle: Activation du parcage d’appel pour les utilisateurs
ms:assetid: 9430763f-3394-467c-9c6d-426bf761604e
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398753(v=OCS.15)
ms:contentKeyID: 49298107
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Activation du parcage d’appel pour les utilisateurs dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-11_

Les utilisateurs ne peuvent pas parquer les appels ni récupérer les appels mis en garde tant qu’ils ne sont pas activés pour le parcage d’appel dans la stratégie de voix.

> [!NOTE]  
> Par défaut, le parcage d’appel est désactivé pour tous les utilisateurs.

Vous pouvez activer le parcage d’appel au niveau de l’étendue globale ou au niveau de l’étendue du site ou de l’utilisateur. L’étendue d’utilisateur est prioritaire sur l’étendue du site et l’étendue du site est prioritaire sur l’étendue globale. Si vous avez plusieurs stratégies de voix, passez-les en revue pour activer le parcage d’appel, et pas seulement la stratégie globale.

## Pour utiliser le Panneau de configuration Lync Server pour activer le parcage d’appel pour les utilisateurs

1.  Ouvrez une session sur l’ordinateur en tant que membre du groupe **RTCUniversalServerAdmins** ou membre du rôle d’administrateur **CsVoiceAdministrator** , **CsServerAdministrator** ou **CsAdministrator** .

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales** .

4.  Cliquez sur l’onglet **Stratégie de la voix** .

5.  Double-cliquez sur une stratégie de voix existante pour ouvrir la boîte de dialogue **Modifier la stratégie de voix** .

6.  Sous **Fonctionnalités d’appel** , sélectionnez **Activer le parcage d’appel** .

7.  Cliquez sur **OK** pour enregistrer la stratégie de voix.

## Pour utiliser les applets de commande pour activer le parcage d’appel pour les utilisateurs

1.  Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins, ou en tant que membre du rôle d’administrateur CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Exécutez :
    
        Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
    
    Par exemple, pour activer le parcage d’appel pour la stratégie de voix globale par défaut :
    
        Set-CsVoicePolicy -EnableCallPark $true

## Voir aussi

#### Tâches

[Créer une stratégie et voix et configurer les enregistrements d’utilisation PSTN dans Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)

