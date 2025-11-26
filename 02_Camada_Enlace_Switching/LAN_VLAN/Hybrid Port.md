Semelhante a uma [[Trunk port]], uma hybrid port permite que quadros de várias [[VLAN]]s passem por ela. Diferentemente de uma trunk port, uma porta híbrida pode encaminhar quadros sem marcação para qualquer [[VLAN]].

As hybrid ports são úteis em alguns cenários especiais. Por exemplo, você pode configurar portas híbridas para permitir que [[host]]s em[[ VLAN]]s diferentes se comuniquem com o mesmo [[host]].

![[HybridPort.png]]

Conforme mostrado na página anterior, o PCA envia um quadro para o PCC. O quadro é marcado com a [[VLAN]] 10 na porta híbrida conectada ao PCA. Quando chega à porta conectada ao PCC, a porta retira a tag [[VLAN]] 10 do quadro e o envia ao PCC. Da mesma forma, os quadros marcados com a [[VLAN]] 20 podem chegar ao PCC porque a porta conectada ao PCC pode encaminhar os quadros sem marcação. No entanto, os quadros do PCA não podem chegar ao PCB, pois a porta conectada ao PCB não permite a passagem dos quadros da [[VLAN]] 10.

Conforme descrito anteriormente, uma função importante da tecnologia [[VLAN]] é segmentar uma [[WLAN]]]] em grupos de trabalho virtuais com base na organização e não na localização física. Todas as estações de trabalho e servidores em um grupo de trabalho panicular podem ser atribuídos à mesma [[VLAN]], independentemente de suas localizações físicas na [[WLAN]]]]. Portanto, uma [[VLAN]] pode abranger vários [[switch]]es.

Para garantir que os [[host]]s em uma [[VLAN]] possam se comunicar entre si, as tags de [[VLAN]] dos quadros [[Ethernet]] devem ser mantidas quando forem transmitidas entre os [[switch]]es.