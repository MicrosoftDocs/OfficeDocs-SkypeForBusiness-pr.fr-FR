---
title: 'Lync Server 2013 : Ajout des sites de succursale à votre topologie'
TOCTitle: Ajout des sites de succursale à votre topologie
ms:assetid: b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412905(v=OCS.15)
ms:contentKeyID: 49298640
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ajout des sites de succursale à votre topologie dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-05_

Les sites de succursale représentent des filiales physiques connectées à vos bureaux principaux via une liaison réseau étendu. Pour ajouter un site de succursale à votre topologie Lync, exécutez la procédure suivante sur le site central.

## Pour ajouter des sites de succursale à votre topologie

1.  Cliquez sur **Démarrer** , sur **Tous les programmes** , sur **Microsoft Lync Server** , puis sur **Générateur de topologie Lync Server** .

2.  Dans l’arborescence de la console, développez le site central, cliquez avec le bouton droit sur **Sites de succursale** , puis cliquez sur **Nouveau site de succursale** .

3.  Dans la boîte de dialogue **Définir un nouveau site de succursale**, cliquez sur **Nom**, puis saisissez le nom du site de succursale.

4.  (Facultatif) Cliquez sur **Description**, puis entrez une description explicite de ce site.

5.  Cliquez sur **Suivant** .

6.  (Facultatif) Dans la boîte de dialogue **Définir un nouveau site de succursale** suivante, effectuez les opérations suivantes :
    
      - Cliquez sur **Ville**, puis indiquez le nom de la ville où le site de succursale est basé.
    
      - Cliquez sur **Dép./Région**, puis indiquez le nom du département ou de la région où le site de succursale est basé.
    
      - Cliquez sur **Code du pays** , puis tapez le code d’appel à deux chiffres du pays ou de la région du site de succursale.

7.  Cliquez sur **Suivant** et effectuez l’une des opérations suivantes :
    
      - Si vous utilisez un Survivable Branch Appliance ou un serveur sur ce site, assurez-vous que la case à cocher **Ouvrir l’Assistant Nouveau Survivable Branch Appliance à la fermeture de cet Assistant** est activée, cliquez sur **Terminer** , puis suivez les instructions de l’Assistant qui s’affiche. Pour obtenir des informations sur les éléments de l’Assistant, reportez-vous à [Définition d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server dans Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).
    
      - Si vous n’utilisez pas de Survivable Branch Appliance ou de serveur sur ce site, désactivez la case à cocher **Ouvrir l’Assistant Nouveau Survivable Branch Appliance à la fermeture de cet Assistant** , puis cliquez sur **Terminer** .

8.  Répétez les étapes précédentes pour chaque site de succursale que vous souhaitez ajouter à la topologie.

**Étape suivante :**

Pour les serveurs Survivable Branch Appliance ou Survivable Branch Server : [Définition d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server dans Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)

Pour la connectivité RTC non résiliante : [Définition d’une passerelle RTC pour un site de succursale dans Lync Server 2013](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md), [Configuration d’une jonction avec la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) ou [Configuration d’une jonction sans déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)

