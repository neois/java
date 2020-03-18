# java
private String padLeftByte(String inputString, int length, String padString) {
	    byte[] temp;
	   
	    String str = inputString;
		try {
			temp = str.getBytes("EUC-KR");
			
			while (temp.length > length) {
				
				str = inputString.substring(0,str.length()-1);
				temp = str.getBytes("EUC-KR");
		    }
			
			
		    StringBuilder sb = new StringBuilder();
		    sb.append(str);
		    for (int i = 0; i < length - temp.length; i++) {
		        sb.append(padString);
		    }
		    
		    byte[] data;
	 
			data = sb.toString().getBytes("EUC-KR");
			//StringUtil.logger(sb.toString() +":"+ data.length);
	 	
			 return sb.toString();
			 
		} catch (UnsupportedEncodingException e1) {
			StringUtil.logger(e1);
		}
	   return "";
	}
