---
title: "Lync Server 2013 : Ajout d’un site de succ. SBA Lync Server 2013 à votre top."
TOCTitle: Ajout d’un site de succursale Survivable Branch Appliance Lync Server 2013 à votre topologie
ms:assetid: d3142a37-4606-456d-8ea9-6cc0e51e55f3
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ721896(v=OCS.15)
ms:contentKeyID: 49891557
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ajout d’un site de succursale Survivable Branch Appliance Lync Server 2013 à votre topologie

 

_**Dernière rubrique modifiée :** 2012-10-07_

Les serveurs Survivable Branch ApplianceMicrosoft Lync Server 2013 (SBA) ne peuvent pas être associés à un pool de serveurs frontauxMicrosoft Lync Server 2010 comme serveur d’inscriptions de sauvegarde. Un SBA doit être associé à un pool de serveurs frontauxMicrosoft Lync Server 2013. Ces étapes impliquent la présence d’un SBA Microsoft Lync Server 2013. Cette procédure doit être effectuée sur le site central.

## Pour ajouter des sites de succursale avec un SBA Microsoft Lync Server 2013 à votre topologie

1.  Démarrez le Générateur de topologie : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Générateur de topologie Lync Server**.

2.  Dans l’arborescence de la console, développez successivement le site central, **Sites de succursale**, puis cliquez sur **Nouveau site de succursale**.

3.  Dans la boîte de dialogue **Définir un nouveau site de succursale**, cliquez sur **Nom**, puis tapez un nom pour le nouveau site de succursale.

4.  (Facultatif) Cliquez sur **Description**, puis saisissez une description explicite du site de succursale.

5.  Cliquez sur **Suivant**.

6.  (Facultatif) Dans la boîte de dialogue **Définir un nouveau site de succursale** suivante, effectuez les opérations suivantes :
    
      - Cliquez sur **Ville**, puis saisissez le nom de la ville où le site de succursale est basé.
    
      - Cliquez sur **Dép./Région**, puis indiquez le nom du département ou de la région où le site de succursale est basé.
    
      - Cliquez sur **Code du pays**, puis tapez le code d’appel à deux chiffres du pays ou de la région du site de succursale.

7.  Cliquez sur **Suivant**, puis effectuez l’une des opérations suivantes :
    
      - Si vous utilisez un Survivable Branch Appliance ou un serveur Survivable Branch Server sur ce site, vérifiez que la case **Ouvrir l’Assistant Nouveau Survivable Branch Appliance à la fermeture de cet Assistant** est cochée.
    
      - Si vous n’utilisez pas de Survivable Branch Appliance ou de serveur Survivable Branch Server sur ce site, décochez la case **Ouvrir l’Assistant Nouveau Survivable Branch Appliance à la fermeture de cet Assistant**.
    
      - Cliquez sur **Terminer**, puis suivez les instructions de l’Assistant qui s’ouvre. Pour plus d’informations sur les éléments de l’Assistant, reportez-vous à [Définition d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server dans Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).

8.  Répétez les étapes précédentes pour chaque site de succursale que vous souhaitez ajouter à la topologie.

## Voir aussi

#### Tâches

[Définition d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server dans Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)  
[Définition d’une passerelle RTC pour un site de succursale dans Lync Server 2013](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)  
[Configuration d’une jonction avec la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Configuration d’une jonction sans déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)

