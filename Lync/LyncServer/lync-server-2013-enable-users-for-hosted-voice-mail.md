---
title: "Lync Server 2013 : Activ. des utilisateurs pour la messagerie vocale hébergée"
TOCTitle: Activation des utilisateurs pour la messagerie vocale hébergée
ms:assetid: fa559f8f-ef99-43a1-b580-9e998b95efb8
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg413062(v=OCS.15)
ms:contentKeyID: 49299406
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Activation des utilisateurs pour la messagerie vocale hébergée dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-24_

Procédez comme suit pour activer la messagerie vocale pour les utilisateurs Lync Server 2013 sur un service de messagerie unifiée Exchange hébergée.

Pour plus d’informations, reportez-vous à [Gestion des utilisateurs Exchange hébergés dans Lync Server 2013](lync-server-2013-hosted-exchange-user-management.md) dans la documentation de planification.

Pour plus d’informations sur l’applet de commande [Set-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsUser), reportez-vous à la documentation Lync Server Management Shell.

> [!IMPORTANT]  
> Avant de pouvoir activer un utilisateur Lync Server 2013 pour la messagerie vocale hébergée, vous devez déployer une stratégie de messagerie vocale hébergée s’appliquant à son compte d’utilisateur. Pour plus d’informations, reportez-vous à <a href="lync-server-2013-hosted-voice-mail-policies.md">Stratégies de messagerie vocale hébergées dans Lync Server 2013</a>.

## Pour activer les utilisateurs pour la messagerie vocale hébergée

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Exécutez l’applet de commande Set-CsUser pour configurer le compte d’utilisateur pour la messagerie vocale hébergée. Par exemple, exécutez :
    
        Set-CsUser -HostedVoiceMail $True -Identity "contoso\kenmyer"
    
    L’exemple qui précède définit les paramètres suivants :
    
      - **HostedVoiceMail** permet d’acheminer les appels de la messagerie vocale d’un utilisateur vers la messagerie unifiée Exchange hébergée. Il signale également à Microsoft Lync 2013 qu’il faut allumer l’indicateur « Appeler la messagerie vocale ».
    
      - **Identity** indique le compte d’utilisateur à modifier. Vous pouvez définir la valeur « Identity » dans l’un des formats suivants :
        
          - l’adresse SIP de l’utilisateur ;
        
          - le nom d’utilisateur principal Active Directory ;
        
          - le nom de domaine et le nom d’ouverture de session de l’utilisateur (par exemple, contoso\\kenmyer) ;
        
          - le nom complet des services de domaine Active Directory de l’utilisateur (par exemple, Ken Myer). Vous pouvez recourir à l’astérisque (caractère générique \*) si vous utilisez le nom complet comme « Identity » pour l'utilisateur. Par exemple « Identity \* Smith » renvoie tous les utilisateurs dont le nom complet se termine par la valeur de chaîne « Smith ».
        
        > [!NOTE]  
        > Le nom de compte SAM Active Directory de l’utilisateur ne peut pas être utilisé comme valeur « Identity », car il n’est pas forcément unique dans la forêt.
