---
title: Installation du package de compatibilité descendante WMI
TOCTitle: Installation du package de compatibilité descendante WMI
ms:assetid: 38797fbd-06a0-4008-b099-158e7b5d7703
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204816(v=OCS.15)
ms:contentKeyID: 49296882
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Installation du package de compatibilité descendante WMI

 

_**Dernière rubrique modifiée :** 2012-10-02_

Si vous essayez d’exécuter l’Assistant Fusion du générateur de topologie sans installer le package de compatibilité descendante WMI, le message d’erreur suivant s’affiche :

![Message d’erreur WMI](images/JJ204816.a007d2f2-fc85-430c-91eb-382b032469af(OCS.15).jpg "Message d’erreur WMI")

Si vous essayez d’exécuter l’applet de commande **Merge-CsLegacytopology** sans installer le package de compatibilité descendante WMI, le message d’erreur suivant s’affiche :

![Erreur de fournisseur WMI Windows PowerShell](images/JJ204816.c510824e-1807-4c7e-bb28-c6cfea2eac1d(OCS.15).jpg "Erreur de fournisseur WMI Windows PowerShell")

Pour installer le package de compatibilité descendante WMI

1.  Sur votre support d’installation, accédez à \\SETUP\\AMD64\\SETUP\\OCSWMIBC.MSI.

2.  Installez OCSWMIBC.MSI.
    
    > [!IMPORTANT]  
    > OCSWMIBC.msi doit être installé sur l’ordinateur sur lequel l’Assistant Fusion du générateur de topologie s’exécute. Cependant, nous recommandons d’installer OCSWMIBC.msi sur tous les serveurs frontaux de votre topologie.    
    > [!IMPORTANT]  
    > OCSWMIBC.msi peut être installé sur tout ordinateur du domaine sur lequel les composants principaux de Lync Server 2013 et Lync Server 2013 Management Shell sont installés, et ayant accès à la topologie Office Communications Server 2007 R2 (fournisseur WMI des services de domaine Active Directory (AD DS) et SQL Server).
